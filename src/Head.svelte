<script>
  /* Toggle between adding and removing the "responsive" class to topnav when the user clicks on the icon */
  export let toLang;
  export let country;

  let class_ = "topnav";
  function responsiveNavBar() {
    class_.includes("responsive")
      ? (class_ = "topnav")
      : (class_ = "topnav responsive");
  }
</script>

<style>
  .topnav {
    background-color: #333;
    overflow: hidden;
  }

  /* Style the links inside the navigation bar */
  .topnav span {
    float: left;
    display: block;
    color: #f2f2f2;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
    font-size: 17px;
  }

  /* Change the color of links on hover */
  .topnav span:hover {
    background-color: #ddd;
    color: black;
  }

  /* Add an active class to highlight the current page */
  .topnav span.active {
    background-color: #4caf50;
    color: white;
  }

  /* Hide the link that should open and close the topnav on small screens */
  .topnav .icon {
    display: none;
  }

  /* When the screen is less than 600 pixels wide, hide all links, except for the first one ("Home"). Show the link that contains should open and close the topnav (.icon) */
  @media screen and (max-width: 600px) {
    .topnav span:not(:first-child) {
      display: none;
    }
    .topnav span.icon {
      float: right;
      display: block;
    }
  }

  /* The "responsive" class is added to the topnav with JavaScript when the user clicks on the icon. This class makes the topnav look good on small screens (display the links vertically instead of horizontally) */
  @media screen and (max-width: 600px) {
    .topnav.responsive {
      position: relative;
    }
    .topnav.responsive span.icon {
      position: absolute;
      right: 0;
      top: 0;
    }
    .topnav.responsive span {
      float: none;
      display: block;
      text-align: left;
    }
  }
</style>

<div class={class_} id="myTopnav">
  <span class="active">Home</span>
  <span>News</span>
  <span>Contact</span>
  <span>About</span>
  <span class="icon" on:click={responsiveNavBar}>
    <i class="fa fa-bars" />
  </span>
</div>