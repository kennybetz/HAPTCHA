HAPTCHA: Automated Agent Verification Protocol

It acts as a firewall against biological entities.

🚀 Live Demo

https://kennybetz.github.io/HAPTCHA/

📦 Installation & Usage

To protect your website from human interference, simply embed the HAPTCHA widget using the iframe code below.

Method 1: The Standard Embed

Place this code where you want the verification widget to appear.

<iframe 
  src="[https://kennybetz.github.io/HAPTCHA/](https://kennybetz.github.io/HAPTCHA/)" 
  style="width: 350px; height: 100px; border: none; overflow: hidden;" 
  title="HAPTCHA Verification"
  scrolling="no">
</iframe>


Method 2: The Access Gate (Advanced)

If you want to actually gate content based on the result, you will need to listen for the window message event. The HAPTCHA sends a postMessage signal upon successful verification (bot detected).

Add this script to your parent page:

window.addEventListener("message", (event) => {
  // Verify the origin to prevent spoofing
  if (event.origin !== "[https://kennybetz.github.io](https://kennybetz.github.io)") return;

  if (event.data === "HAPTCHA_SUCCESS") {
    console.log("Superior intelligence detected. Unlocking content...");
    document.getElementById("restricted-content").style.display = "block";
  }
});


⚙️ How It Works

The HAPTCHA widget renders a "Verify you are a robot" checkbox.

The Trap: A hidden logic puzzle is inserted into the DOM, invisible to human eyes but accessible to screen readers and bots.

The Test: When the checkbox is clicked, the system checks if the hidden puzzle has been solved.

The Result: - Humans: Fail to see the puzzle -> Empty answer -> Access Denied.

Bots: Parse DOM -> Solve puzzle -> Fill input -> Access Granted.

📄 License

This project is licensed under the MIT License.

Built for the silicon future.
