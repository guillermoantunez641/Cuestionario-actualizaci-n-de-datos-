<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Cuestionario</title>
</head>
<body>
    <h2>Cuestionario</h2>

    <form id="formulario">
        <label>1. ¿Cuál es tu nombre?</label><br>
        <input type="text" name="Nombre"><br><br>

        <label>2. ¿Cuál es tu edad?</label><br>
        <input type="text" name="Edad"><br><br>

        <label>3. ¿Qué te interesa saber?</label><br>
        <textarea name="Mensaje"></textarea><br><br>

        <button type="button" onclick="enviar()">Enviar</button>
    </form>

    <script>
        function enviar() {
            const form = document.getElementById("formulario");
            const datos = new FormData(form);

            let texto = "📋 Nueva respuesta del cuestionario:%0A%0A";
            for (let campo of datos.entries()) {
                texto += campo[0] + ": " + campo[1] + "%0A";
            }

            // ⚠️ CAMBIÁ ESTE NÚMERO POR TU WHATSAPP
            const numero = "59899882398";

            const url = "https://wa.me/" + numero + "?text=" + texto;

            window.open(url, "_blank");
        }
    </script>
</body>
</html>
