# SPEC — Keep Calm v1
Objectivo: gerar posters clássicos personalizáveis, mobile-first, offline e sem custos de backend.
Texto predefinido KEEP / CALM / AND + CARRY ON; ambos editáveis, maiúsculas, quebra de linha automática e ajuste de tamanho. Fundo e texto com paleta e selector livre. Coroa, coração, avião, café ou taça; símbolo ocultável. Pré-visualização e PNG partilham o mesmo canvas 2000×3000, evitando diferenças na exportação. Guardar automaticamente preferências locais; repor valores iniciais. Sem sincronização ou recolha de dados.
Arquitectura: HTML/CSS/JS nativo, Canvas + Path2D, manifest e Service Worker. Rede primeiro com fallback offline. Preferências: keep-calm-v1 em localStorage. Exportar PNG; Web Share API com fallback para download. Todos os assets locais.

Interface v2: poster ocupa o ecrã disponível; toque no topo para ilustração, centro para texto/tinta e rodapé para fundo. Controlos em diálogos nativos, fecho por botão/Escape/toque exterior. Barra superior com ícones de repor, PNG, partilha e instalação quando disponível. Preferências existentes preservadas.
