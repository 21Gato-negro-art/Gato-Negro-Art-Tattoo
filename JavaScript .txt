const button = document.getElementById("language");
const whatsapp = document.getElementById("whatsapp");
let english = false;

button.addEventListener("click", () => {
  english = !english;
  document.documentElement.lang = english ? "en" : "es";
  button.textContent = english ? "ES" : "EN";

  document.querySelectorAll("[data-es]").forEach(element => {
    element.textContent = english ? element.dataset.en : element.dataset.es;
  });

  const message = english
    ? "Hi Gato Negro, I would like to ask about a tattoo."
    : "Hola Gato Negro, me gustaría consultar sobre un tatuaje.";

  whatsapp.href = "https://wa.me/50672704061?text=" + encodeURIComponent(message);
});
