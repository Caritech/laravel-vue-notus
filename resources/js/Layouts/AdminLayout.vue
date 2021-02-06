<template>
    <div>
        <sidebar />
        <div class="relative md:ml-64 bg-gray-200">
            <admin-navbar />
            <header-stats />
            <div class="px-4 md:px-10 mx-auto w-full -m-24">
                <slot></slot>
                <footer-admin />
            </div>
        </div>
    </div>
</template>
<script>
import AdminNavbar from "@/Components/Navbars/AdminNavbar.vue"
import Sidebar from "@/Components/Sidebar/Sidebar.vue"
import HeaderStats from "@/Components/Headers/HeaderStats.vue"
import FooterAdmin from "@/Components/Footers/FooterAdmin.vue"
export default {
    name: "admin-layout",
    components: {
        AdminNavbar,
        Sidebar,
        HeaderStats,
        FooterAdmin,
    },
}
</script>
