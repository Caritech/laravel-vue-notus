<template>
    <div>
        <a
            class="hover:text-gray-600 text-gray-800 px-3 py-2 flex items-center text-xs uppercase font-bold"
            href="#pablo"
            ref="btnDropdownRef"
            v-on:click="toggleDropdown($event)"
        >
            Demo Pages
        </a>
        <div
            ref="popoverDropdownRef"
            class="bg-white text-base z-50 float-left py-2 list-none text-left rounded shadow-lg min-w-48"
            v-bind:class="{
        hidden: !dropdownPopoverShow,
        block: dropdownPopoverShow,
      }"
        >
            <span class="text-sm pt-2 pb-0 px-4 font-bold block w-full whitespace-no-wrap bg-transparent text-gray-500">
                Admin Layout
            </span>
            <a
                href="/admin/dashboard"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Dashboard
            </a>
            <a
                href="/admin/settings"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Settings
            </a>
            <a
                href="/admin/tables"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Tables
            </a>
            <a
                href="/admin/maps"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Maps
            </a>
            <div class="h-0 mx-4 my-2 border border-solid border-gray-200" />
            <span class="text-sm pt-2 pb-0 px-4 font-bold block w-full whitespace-no-wrap bg-transparent text-gray-500">
                Auth Layout
            </span>
            <a
                href="/auth/login"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Login
            </a>
            <a
                href="/auth/register"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Register
            </a>
            <div class="h-0 mx-4 my-2 border border-solid border-gray-200" />
            <span class="text-sm pt-2 pb-0 px-4 font-bold block w-full whitespace-no-wrap bg-transparent text-gray-500">
                No Layout
            </span>
            <a
                href="/landing"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Lading
            </a>
            <a
                href="/profile"
                class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
            >
                Profile
            </a>
        </div>
    </div>
</template>
<script>
import { createPopper } from "@popperjs/core"

export default {
    data() {
        return {
            dropdownPopoverShow: false,
        }
    },
    methods: {
        toggleDropdown: function (event) {
            event.preventDefault()
            if (this.dropdownPopoverShow) {
                this.dropdownPopoverShow = false
            } else {
                this.dropdownPopoverShow = true
                createPopper(
                    this.$refs.btnDropdownRef,
                    this.$refs.popoverDropdownRef,
                    {
                        placement: "bottom-start",
                    }
                )
            }
        },
    },
}
</script>
