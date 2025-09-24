<script>
export default {
    data() {
        return {
            name: '',
            job: '',
            bio: '',
            imageUrl: '/assets/head1.jpg',
            bgColor: '',   // will be set in mounted()
            textColor: '',
            themes: [
                { bg: '#333', text: '#fff' },     // dark
                { bg: '#fff', text: '#000' },     // light
                { bg: '#39ff14', text: '#000' }   // neon
            ],
            currentThemeIndex: 0
        }
    },
    methods: {
        cycleTheme() {
            // Move to the next theme
            this.currentThemeIndex = (this.currentThemeIndex + 1) % this.themes.length;
            const theme = this.themes[this.currentThemeIndex];
            this.bgColor = theme.bg;
            this.textColor = theme.text;
        }
    },
    mounted() {
        // Set the initial theme on load
        const theme = this.themes[this.currentThemeIndex];
        this.bgColor = theme.bg;
        this.textColor = theme.text;
    }
}
</script>

<template>
    <div class="container">
        <!-- Form Section -->
        <div class="form-section"
             :style="{ backgroundColor: bgColor, color: textColor }">
            <h2>Customize Profile</h2>

            <label>Name:</label><br>
            <input v-model="name" placeholder="Your Name"
                   :style="{ backgroundColor: bgColor, color: textColor, borderColor: textColor }"><br><br>

            <label>Job Title:</label><br>
            <input v-model="job" placeholder="Web Developer"
                   :style="{ backgroundColor: bgColor, color: textColor, borderColor: textColor }"><br><br>

            <label>Bio:</label><br>
            <textarea v-model="bio" rows="3" placeholder="A short bio..."
                      :style="{ backgroundColor: bgColor, color: textColor, borderColor: textColor }"></textarea><br><br>

            <label>Profile Image URL:</label><br>
            <input v-model="imageUrl" placeholder="https://example.com/me.jpg"
                   :style="{ backgroundColor: bgColor, color: textColor, borderColor: textColor }"><br><br>

            <label>Theme Presets:</label><br>
            <button class="theme-button"
                    :style="{ backgroundColor: bgColor, color: textColor, borderColor: textColor }"
                    @click="cycleTheme">Cycle theme</button>
        </div>

        <!-- Preview Section -->
        <div class="preview-section">
            <h2>Live Preview</h2>
            <div class="preview-card"
                 :style="{ backgroundColor: bgColor, color: textColor }">
                <img :src="imageUrl" class="preview-img">
                <h3>{{ name || 'Your Name' }}</h3>
                <h4>{{ job || 'Job Title' }}</h4>
                <p>{{ bio || 'Write something about yourself...' }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    gap: 20px;
    padding: 20px;
    font-family: sans-serif;
}

.form-section,
.preview-section {
    width: 50%;
}

.preview-card {
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    transition: all 0.3s ease;
}

.preview-img {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
    margin-bottom: 10px;
}

input, textarea {
    padding: 5px;
    border-radius: 4px;
    border: 1px solid;
    width: 100%;
    box-sizing: border-box;
}

.theme-button {
    margin: 5px;
    padding: 5px 10px;
    border: 1px solid;
    border-radius: 4px;
    cursor: pointer;
}
</style>
