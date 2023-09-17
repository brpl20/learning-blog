<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adobe Premiere Pro Keyboard Shortcuts</title>
    <script src="https://unpkg.com/htmx.org@1.9.4" integrity="sha384-zUfuhFKKZCbHTY6aRR46gxiqszMk5tcHjsVFxnUo8VMus4kHGVdIYVbOYYNlKmHV" crossorigin="anonymous"></script>
    <style>
        table {
            border-collapse: collapse;
            width: 80%;
            margin: 50px auto;
        }

        table, th, td {
            border: 1px solid black;
        }

        th, td {
            padding: 15px;
            text-align: left;
        }

        th {
            background-color: #f2f2f2;
        }

        kbd {
            padding: 2px 5px;
            font-family: monospace;
            border: 1px solid #aaa;
            border-radius: 3px;
            background-color: #f7f7f7;
            box-shadow: inset 0 1px 0 #fff, 0 1px 0 #aaa;
        }
    </style>
</head>
<body>

# Teste Mistura com HTML e MD 


# Fim Teste 

<h2 style="text-align:center;">Adobe Premiere Pro Keyboard Shortcuts</h2>

<div> 
    <table>
        <thead>
            <tr>
                <th>Shortcut</th>
                <th>Function</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><kbd>Ctrl</kbd> + <kbd>N</kbd></td>
                <td>New Project</td>
            </tr>
            <tr>
                <td><kbd>Ctrl</kbd> + <kbd>S</kbd></td>
                <td>Save</td>
            </tr>
            <tr>
                <td><kbd>Space</kbd></td>
                <td>Play/Pause</td>
            </tr>
            <tr>
                <td><kbd>J - K - L</kbd></td>
                <td>Zoom In - Voltar ao Zoom Timeline - Zoom Out</td>
            </tr>
            <tr>
               <td><kbc>Ctrl</kbd><kbd>+</kbd><kbd>J - K - L</kbd></td>
                <td>Fast BackWard - Pause - Fast ForWard</td>
            </tr>
            <tr>
                <td><kbc>Command (Alt)</kbd><kbd>+</kbd><kbd>+/-</kbd></td>
                <td>ZoomIn / Zoom Out Audio</td>
            </tr>
            <tr>
               <td><kbc>Shift</kbd><kbd>+</kbd><kbd>1 - 2 - 3 - 4 - 5 - 6 - 7 - 8 - 9 </kbd></td>
               <td>Projects (1) - Source Monitor (2) - Timelines (3) - Program - Effect Controls (5) - Audio Track - Effects (7) - Media Browser - Audio Clip Mixer (9) - Toggle Multi - Minimize All Tracks (-) - Expand All Tracks (+)</td>
            </tr>
            </tr>
            <tr>
                <td><kbd>C</kbd></td>
                <td>Razor Tool</td>
            </tr>
            <tr>
                <td><kbd>V</kbd></td>
                <td>Selection Tool</td>
            </tr>
            <tr>
                <td><kbd>I</kbd></td>
                <td>Mark In</td>
            </tr>
            <tr>
                <td><kbd>O</kbd></td>
                <td>Mark Out</td>
            </tr>
            <tr>
                <td><kbd>+</kbd></td>
                <td>Zoom In</td>
            </tr>
            <tr>
                <td><kbd>-</kbd></td>
                <td>Zoom Out</td>
            </tr>
            <tr>
                <td><kbd>Up Arrow</kbd></td>
                <td>Previous Edit Point</td>
            </tr>
            <tr>
                <td><kbd>Down Arrow</kbd></td>
                <td>Next Edit Point</td>
            </tr>
            <!-- You can add more rows with shortcuts as required -->
            <tr>
                <td><kbd>Shift</kbd> + <kbd>[</kbd></td>
                <td>Maximize ? </td>
            </tr>
            <tr>
                <td><kbd>.</kbd> + <kbd>.</kbd></td>
                <td>Effects => Filter Show Only Edited Properties</td>
            </tr>
            <tr>
                <td><kbd>i / o / f</kbd></td>
                <td>Source Trimmer => IN / OUT / Sync Source With Preview</td>
            </tr>
            <tr>
                <td><kbd>, / .</kbd></td>
                <td>Source Trimmer => Insert (empurra) / Overwrite (sobrepõe)</td>
            </tr>
            <tr>
                <td><kbd>Alt + Click</kbd></td>
                <td>Replace (Sobreposição Tamanho Exato)</td>
            </tr>
        </tbody>
    </table>
    
</div>

<div> 
    <table>
        <thead>
            <tr>
                <th>Shortcut (Timeline)</th>
                <th>Function</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><kbd>Shift</kbd> + <kbd>+/-</kbd></td>
                <td>Timeline => Expand / Close Tracks</td>
            </tr>
            <tr>
                <td><kbd>M</kbd></td>
                <td>Timeline => Marker</td>
            </tr>
            <tr>
                <td><kbd>Q - W</kbd></td>
                <td><= Top And Tail Editing =></td>
            </tr>
            <tr>
                <td><kbd>Alt</kbd> + <kbd>Click</kbd></td>
                <td>Timeline => Marker Adjust</td>
            </tr>
            <tr>
                <td><kbd>Shift</kbd> + <kbd>Alt</kbd> + <kbd>S</kbd></td>
                <td>Timeline => Sincronizar</td>
            </tr>
            <tr>
                <td><kbd>Command</kbd> + <kbd>L</kbd></td>
                <td>Timeline => Link/Unlink </td>
            </tr>
            <tr>
                <td><kbd>Command</kbd> + <kbd>Alt</kbd> + <kbd>V</kbd></td>
                <td>Timeline => Paste Attributes </td>
            </tr>
        </tbody>
    </table>
    
</div>


<div> 
    <h2>TODO
        <ul>
          <li>Overshoot (Pequeno Retorno Na Animação) : Zoom de 80 -> 82% (+/- 3% de Diferença): Aula 4.4 (17:48)</li>
          <li>Overshoot : Dá pra fazer nos gráficos também (Adicionar Pequeno Negativo antes do Final)</li>
          <li></li>
          <li></li>
        </ul>
    </h2>
</div>


<div> 
    <h2> Configurações
        <ul>
          <li>Timeline com agulha no centro:</li>
          <li>Audio Format: Na Timeline -> Desmarcar => Rectified Audio Wave Forms</li>
          <li>Media => Default Media Scaling => Set to Frame Size (Para Importar Mais Fácilmente)</li>
          <li>Pesquisar => Audio Transitions</li>
          <li>Pesquisar => htmx.org (melhorar esse manual)</li>
          <li>New Timeline => Pixel Aspect Ratio: Square Pixel (1.0) - Formato da Internet</li>
          <li>New Timeline => Fields: No Fields (Progressive Scan)</li>
          <li>New Timeline => Previews: Quicktime</li>
          <li>New Timeline => Previews: Apple Pro Res 422</li>
          <li>New Timeline => Previews: Maximum Bit Depth</li>
          <li>New Timeline => Previews: Maximum Render Quality</li>
          <li>New Timeline => Previews: Composite in Linear Color</li>
          <li>Restrict Trim => Para restringir limites dos clips/subclips (não dá para expandir com mouse)</li>
          <li>Play Audio When Scrubling => ON/OFF (Qdo estiver arrastando - Scrubling)</li>
          <li>Estudar: Cut in Action --- Match Cut</li>
          <li>Testar: Curte com Q/W e JKL</li>
          <li>Testar: Desfazer corte com Delete</li>
          <li>Preferences => Media => Default Media Scaling: Set to Frame Size</li>
          <li>Blending Mode => https://helpx.adobe.com/br/premiere-pro/using/blending-modes.html</li>
          <li>Praticar => https://bezier.method.ac/</li>
          <li>Mascaras => Pode Copiar e Colar</li>
          <li>Mascaras => Pode Copiar e Colar</li>


        </ul>
    </h2>
</div>




</body>
</html>
