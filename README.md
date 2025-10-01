<script>
    // โหลดสถานะตอนเปิดเว็บ
    window.onload = function() {
      document.querySelectorAll(".card").forEach(card => {
        let name = card.querySelector("strong").innerText; // ใช้ชื่อจาก <strong>
        let owned = localStorage.getItem(name); 
        if (owned === "true") {
          card.classList.add("border-green-500", "bg-green-900");
          card.querySelector("input").checked = true;
        }
      });
    };

    // ฟังก์ชันเวลาติ๊ก checkbox
    function toggleOwned(checkbox) {
      let card = checkbox.closest(".card");
      let name = card.querySelector("strong").innerText;
      let isOwned = checkbox.checked;

      // ล้างของเดิมก่อน แล้วค่อยใส่
      card.classList.remove("border-gray-300", "bg-gradient-to-b", "from-black/30", "to-black/60", "border-green-500", "bg-green-900");

      if (isOwned) {
        card.classList.add("border-green-500", "bg-green-900");
      } else {
        card.classList.add("border-gray-300", "bg-gradient-to-b", "from-black/30", "to-black/60");
      }

      localStorage.setItem(name, isOwned);
    }
  </script>
