<script lang="ts">
  import { cn } from "$lib/utils";

  /**
   * @component
   * Spotlight creates a visual spotlight effect using an animated SVG ellipse
   * with a blur filter. It's typically positioned absolutely within a container.
   *
   * @prop class - Optional CSS classes for positioning and styling the SVG.
   * @prop fill - The fill color of the spotlight ellipse.
   */
  let _class: string = "";
  export let fill: string = ""; // Default fill is handled in the SVG if this is empty
  export { _class as class };
</script>

<svg
  class={cn(
    "animate-spotlight pointer-events-none absolute z-[1] h-[169%] w-[138%] lg:w-[84%] opacity-0", // Base classes including animation trigger
    _class // User-provided classes for positioning
  )}
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 3787 2842"
  fill="none"
>
  <g filter="url(#filter)">
    <ellipse
      cx="1924.71"
      cy="273.501"
      rx="1924.71"
      ry="273.501"
      transform="matrix(-0.822377 -0.568943 -0.568943 0.822377 3631.88 2291.09)"
      fill={fill || "white"} 
      fill-opacity="0.21"
    ></ellipse>
  </g>
  <defs>
    <filter
      id="filter"
      x="0.860352"
      y="0.838989"
      width="3785.16"
      height="2840.26"
      filterUnits="userSpaceOnUse"
      color-interpolation-filters="sRGB"
    >
      <feFlood flood-opacity="0" result="BackgroundImageFix"></feFlood>
      <feBlend
        mode="normal"
        in="SourceGraphic"
        in2="BackgroundImageFix"
        result="shape"
      ></feBlend>
      <feGaussianBlur stdDeviation="151" result="effect1_foregroundBlur_1065_8" 
      ></feGaussianBlur>
    </filter>
  </defs>
</svg>
