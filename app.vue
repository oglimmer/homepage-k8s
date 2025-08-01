<script setup lang="ts">
const colorMode = useColorMode();

useHead({
    title: "kubernetes @ oglimmer.com",
    meta: [
        {
            name: "description",
            content:
                "I manage a Kubernetes cluster with four nodes using Raspberry Pi hardware. It serves as a platform for my personal projects and facilitates my exploration of cloud-native technologies. Below are the services I employ to oversee and manage my Kubernetes setup.",
        },
        { name: "og:type", content: "website" },
        { name: "og:url", content: "https://www.oglimmer.com/k8s" },
        { name: "og:title", content: "kubernetes @ oglimmer.com" },
        {
            name: "og:description",
            content:
                "I manage a Kubernetes cluster with four nodes using Raspberry Pi hardware. It serves as a platform for my personal projects and facilitates my exploration of cloud-native technologies. Below are the services I employ to oversee and manage my Kubernetes setup.",
        },
        { name: "og:image", content: "https://www.oglimmer.com/images/icon.png" },
    ],
    htmlAttrs: {
        lang: "en",
        "data-bs-theme": colorMode.value,
    },
});

watch(colorMode, (_) => {
    useHead({
        htmlAttrs: {
            "data-bs-theme": colorMode.value,
        },
    });
});

const data = [
    // {
    //     imageSrc: "rancher.jpeg",
    //     title: "Rancher",
    //     text: "Container management UI for Kubernetes",
    //     linkData: [
    //         ["https://minilinux.oglimmer.com/", "Dashboard"],
    //         ["https://ranchermanager.docs.rancher.com/", "Documentation"],
    //     ],
    //     techList: "[k8s, dashboard, rancher, management]",
    // },
    {
        imageSrc: "longhorn.jpeg",
        title: "Longhorn Persistent Storage",
        text: "Cloud native distributed block storage for Kubernetes",
        linkData: [
            ["https://longhorn.oglimmer.com/", "Dashboard"],
            ["https://longhorn.io/", "Home page"],
        ],
        techList: "[k8s, longhorn, storage]",
    },
    {
        imageSrc: "traefik.jpeg",
        title: "Traefik Ingress Controller",
        text: "Cloud Native Application Proxy",
        linkData: [
            ["https://traefik.oglimmer.com/", "Dashboard"],
            ["https://traefik.io/traefik/", "Home page"],
        ],
        techList: "[k8s, traefik, reverse-proxy]",
    },
    {
        imageSrc: "registry.jpeg",
        title: "Container Registry",
        text: "Simple and secure container image registry",
        linkData: [
            ["https://registry.oglimmer.com/ui/", "Dashboard"],
            ["https://distribution.github.io/distribution/", "Home page"],
        ],
        techList: "[k8s, docker, container-registry, container]",
    },
    {
        imageSrc: "grafana.jpeg",
        title: "Grafana Monitoring",
        text: "The open platform for beautiful analytics and monitoring",
        linkData: [
            ["https://grafana.oglimmer.de/", "Dashboard"],
            ["https://grafana.com/", "Home page"],
        ],
        techList: "[k8s, dashboard, monitoring, grafana, prometheus, loki]",
    },
    // {
    //     imageSrc: "keel.jpeg",
    //     title: "Keel Continuous Deployment",
    //     text: "Automated Kubernetes deployment",
    //     linkData: [
    //         ["https://keel.oglimmer.com/", "Dashboard"],
    //         ["https://keel.sh/", "Home page"],
    //     ],
    //     techList: "[k8s, deployment, keel, continuous-deployment]",
    // },
    {
        imageSrc: "maven.jpeg",
        title: "Maven Repository",
        text: "Maven based artifacts for JVM ecosystem",
        linkData: [
            ["https://mvn.oglimmer.com/", "Dashboard"],
            ["https://reposilite.com/", "Home page"],
        ],
        techList: "[k8s, mvn, maven, repository]",
    },
    {
        imageSrc: "git-deploy-control.jpeg",
        title: "Release Management UI",
        text: "Custom build system for git based version control",
        linkData: [["https://git-deploy-control.oglimmer.com/", "Dashboard"]],
        techList: "[k8s, continuous-deployment, git, deployment]",
    },
    {
        imageSrc: "haproxy.jpeg",
        title: "HAProxy",
        text: "Network load balancer / layer 4 reverse proxy",
        linkData: [["https://haproxy.oglimmer.com/", "Dashboard"],["https://www.haproxy.org/", "Home page"]],
        techList: "[haproxy, reverse-proxy]",
    },
    {
        imageSrc: "backup.jpeg",
        title: "Cloud-Backup",
        text: "Custom build backup using Google Drive",
        linkData: [["https://backup.oglimmer.com/", "Dashboard"]],
        techList: "[backup, google-drive]",
    },
    {
        imageSrc: "argocd.jpeg",
        title: "Argo CD",
        text: "Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes",
        linkData: [["https://argocd.oglimmer.com/", "Dashboard"]],
        techList: "[k8s, continuous-deployment, git, deployment]",
    },
];

const transformArray = (arr: any) => {
    const chunkSize = 3;
    const result = [];
    for (let i = 0; i < arr.length; i += chunkSize) {
        result.push(arr.slice(i, i + chunkSize));
    }
    return result;
};

const switchColorMode = () => {
    colorMode.preference = colorMode.value === "light" ? "dark" : "light";
    return false;
};

const graphics = ref("comic");
</script>

<template>
    <div class="bg-primary text-white text-center banner-image">
        <nav class="navbar navbar-expand-lg py-3 navbar-dark">
            <div class="container-fluid">
                <a class="navbar-brand font-weight-bold text-uppercase" href="#"></a>
                <div>
                    <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <a href="javascript:void(0);" :onClick="switchColorMode">
                                <span style="font-size: 1.4em">
                                    <span v-if="colorMode.value === 'light'"><font-awesome-icon icon="fa-solid fa-sun" /></span>
                                    <span v-if="colorMode.value === 'dark'"><font-awesome-icon icon="fa-solid fa-moon" /></span>
                                </span>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>

        <div class="container pb-5">
            <div class="row py-5 align-items-center">
                <div class="col-lg-8">
                    <h5 class="display-4 mb-4 font-weight-bold text-white">kubernetes @ oglimmer.com</h5>
                    <p class="h5 aa mb-4 pb-3 text-white-50">
                        I manage a Kubernetes cluster with five nodes using Raspberry Pi hardware. It serves as a platform for my personal projects and
                        facilitates my exploration of cloud-native technologies. Below are the services I employ to oversee and manage my Kubernetes setup.
                    </p>
                </div>
                <div class="col-lg-4 text-lg-right text-center mt-5 mt-lg-0">
                    <div class="banner-phone-image">
                        <img class="tilt-n-move-shaking" src="/images/icon.png" />
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="container mt-3">
        <div class="d-flex justify-content-end">
            <div class="me-2">Graphics:</div>
            <div class="me-2">
                <select v-model="graphics">
                    <option value="neon">Neon</option>
                    <option value="comic">Comic</option>
                    <option value="apocalypse">Apocalypse</option>
                </select>
            </div>
        </div>
     </div>

    <div class="container">
        <div class="row mt-2" v-for="row in transformArray(data)">
            <div class="col-lg-4 mt-4" v-for="item in row">
                <Project :image-src="`./images/${graphics}/${item.imageSrc}`" :title="item.title" :text="item.text" :link-data="item.linkData" :tech-list="item.techList" />
            </div>
        </div>
    </div>

    <footer class="footer mt-auto py-3">
        <div class="container mt-5">
            <span class="text-muted">© Copyright 2004-2024 by oglimmer.com - Oliver Zimpasser - All rights reserved.</span>
        </div>
    </footer>
</template>

<style scoped>
img:hover {
    animation: tilt-n-move-shaking 0.5s linear infinite;
}

@keyframes tilt-n-move-shaking {
    0% {
        transform: translate(0, 0) rotate(0deg);
    }
    25% {
        transform: translate(5px, 5px) rotate(5deg);
    }
    50% {
        transform: translate(0, 0) rotate(0eg);
    }
    75% {
        transform: translate(-5px, 5px) rotate(-5deg);
    }
    100% {
        transform: translate(0, 0) rotate(0deg);
    }
}

.aa {
    line-height: 30px;
}

@media (min-width: 920px) {
    .aa {
        margin-left: 120px;
        margin-right: 120px;
    }
}

@media (max-width: 460px) {
    .navbar-brand.font-weight-bold.text-uppercase::after {
        content: "Web-Tech-Workshop";
        display: block;
    }
}
@media (min-width: 460px) {
    .navbar-brand.font-weight-bold.text-uppercase::after {
        content: "oglimmer's Web-Tech-Workshop";
        display: block;
    }
}

@media (max-width: 992px) {
    .cooking {
        font-size: 1.1em;
        top: -15px;
    }
}
@media (min-width: 992px) {
    .cooking {
        font-size: 1.2em;
        top: -20px;
    }
}
@media (min-width: 1200px) {
    .cooking {
        font-size: 1.3em;
        top: -30px;
    }
}

div h5 {
    font-family: SpecialElite;
}

.cookingContainer {
    position: relative;
}
.cooking {
    font-family: CookingRegular;
    letter-spacing: 10px;
    text-shadow: 3px 3px 1px rgb(150 228 228);
    color: rgb(90 173 181);
    position: absolute;
    left: -10px;
    margin: 0;
    transform: rotate(-10deg);
}

.banner-image {
    background: linear-gradient(rgba(29, 38, 113, 0.8), rgba(195, 55, 100, 0.8)), url(/images/banner-image.jpg);
    background-size: cover;
    background-position: center;
}

a {
    text-decoration: none;
    color: inherit;
    outline: none;
}

a:hover {
    text-decoration: none;
    color: inherit;
}
</style>
