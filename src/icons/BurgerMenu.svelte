<script lang="ts">
export let showMenu: boolean;
export let toggleMenuOverlay: () => void;
</script>

<button on:click={toggleMenuOverlay} class="rounded-full border-blue-100">
  <div id="burger-menu" class:active={showMenu}>
    <svg xmlns="http://www.w3.org/2000/svg" width="75" height="75" viewBox="0 0 200 200">
      <g stroke-width="6.5" stroke-linecap="round">
        <path d="M72 82.286h28.75" fill="#000" fill-rule="evenodd" stroke="#000" />
        <path
          d="M100.75 103.714l72.482-.143c.043 39.398-32.284 71.434-72.16 71.434-39.878 0-72.204-32.036-72.204-71.554"
          fill="none"
          stroke="#000"
        />
        <path d="M72 125.143h28.75" fill="#000" fill-rule="evenodd" stroke="#000" />
        <path
          d="M100.75 103.714l-71.908-.143c.026-39.638 32.352-71.674 72.23-71.674 39.876 0 72.203 32.036 72.203 71.554"
          fill="none"
          stroke="#000"
        />
        <path d="M100.75 82.286h28.75" fill="#000" fill-rule="evenodd" stroke="#000" />
        <path d="M100.75 125.143h28.75" fill="#000" fill-rule="evenodd" stroke="#000" />
      </g>
    </svg>
  </div>
</button>

<style>
:global(#burger-menu) {
  @apply cursor-pointer flex;
}

svg {
  transition: transform 500ms cubic-bezier(0.4, 0, 0.2, 1);
}

path {
  transition: transform 500ms cubic-bezier(0.4, 0, 0.2, 1),
    stroke-dasharray 500ms cubic-bezier(0.4, 0, 0.2, 1),
    stroke-dashoffset 500ms cubic-bezier(0.4, 0, 0.2, 1);
}

path:nth-child(1) {
  transform-origin: 36% 40%;
}

path:nth-child(2) {
  stroke-dasharray: 29 299;
}

path:nth-child(3) {
  transform-origin: 35% 63%;
}

path:nth-child(4) {
  stroke-dasharray: 29 299;
}

path:nth-child(5) {
  transform-origin: 61% 52%;
}

path:nth-child(6) {
  transform-origin: 62% 52%;
}

.active svg {
  transform: rotate(90deg);
}

.active path:nth-child(1) {
  transform: translateX(9px) translateY(1px) rotate(45deg);
}

.active path:nth-child(2) {
  stroke-dasharray: 225 299;
  stroke-dashoffset: -72px;
}

.active path:nth-child(3) {
  transform: translateX(9px) translateY(1px) rotate(-45deg);
}

.active path:nth-child(4) {
  stroke-dasharray: 225 299;
  stroke-dashoffset: -72px;
}

.active path:nth-child(5) {
  transform: translateX(9px) translateY(1px) rotate(-45deg);
}

.active path:nth-child(6) {
  transform: translateX(9px) translateY(1px) rotate(45deg);
}
</style>
