<script setup lang="ts">
const user = {
    name: 'Jessica',
    surname: 'Randall',
    imageURL: new URL('../assets/images/avatar-jessica.jpeg', import.meta.url).href,
    country: 'United Kingdom',
    city: 'London',
    bio: '"Front-end developer and avid reader."',
    socialMediaLinks: [
        {
            name: 'GitHub',
            url: 'github.com/'
        },
        {
            name: 'Frontend Mentor',
            url: 'frontendmentor.io/'
        },
        {
            name: 'LinkedIn',
            url: 'linkedin.com/'
        },
        {
            name: 'Twitter',
            url: 'twitter.com/'
        },
        {
            name: 'Instagram',
            url: 'instagram.com/'
        }
    ]
}
</script>

<template>
    <main class="container">
        <div class="profile-card">
            <div class="profile-picture-container">
                <img 
                    :src="user.imageURL" 
                    alt="avatar of the user"
                    class="profile-picture"
                >
            </div>


            <div class="profile-info">
                <h1 class="profile-title">
                    {{ user.name }} {{ user.surname }}
                </h1>

                <h2 class="profile-location">
                    {{ user.city }}, {{ user.country }}
                </h2>
            </div>

            <p class="profile-bio">
                {{ user.bio }}
            </p>

            <ul class="profile-social-links">
                <li 
                    v-for="link in user.socialMediaLinks" 
                    :key="link.name"
                    class="profile-social-link-item"
                >
                    <a 
                        :href="`https://${link.url}`" 
                        target="_blank"
                        class="profile-social-link-button"
                    >
                        {{ link.name }}
                    </a>
                </li>
            </ul>
        </div>
    </main>
</template>

<style scoped>
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    min-height: 100vh;
    padding: 7.25rem 1.5rem;
    background-color: var(--black);
}

.profile-card {
    width: 100%;
    max-width: 24rem;
    padding: 1.5rem;
    border-radius: 0.75rem;
    background-color: var(--dark-gray);

    @media (min-width: 640px) {
        padding: 2.5rem;
    }
}

.profile-picture-container {
    display: flex;
    justify-content: center;
}

.profile-picture {
    width: 5.5rem;
    height: 5.5rem;
    border-radius: 50%;
}

.profile-info {
    margin: 1.5rem 0;
}

.profile-title {
    margin-bottom: 0.25rem;
    font-size: 1.5rem;
    font-weight: 600;
    line-height: 150%;
    color: #fff;
    text-align: center;
}

.profile-location {
    font-size: 0.875rem;
    font-weight: 700;
    line-height: 150%;
    color: var(--neon-green);
    text-align: center;
}

.profile-bio {
    margin-bottom: 1.5rem;
    line-height: 150%;
    color: #fff;
    text-align: center;
}

.profile-social-links {
    list-style: none;
    padding: 0;
}

.profile-social-link-item:not(:last-child) {
    margin-bottom: 1rem;
}

.profile-social-link-button {
    display: block;
    width: 100%;
    padding: 0.75rem;
    font-weight: 700;
    line-height: 150%;
    color: #fff;
    text-align: center;
    text-decoration: none;
    background-color: var(--gray);
    border-radius: 0.5rem;
    transition: all 0.3s ease;
}

.profile-social-link-button:hover {
    background-color: var(--neon-green);
    color: var(--gray);
}
</style>