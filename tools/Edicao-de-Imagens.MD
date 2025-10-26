## Extraíndo imagens de arquivos .pak

Prototype Pak Tool
https://github.com/0mateus/prototypepaktool

Ferramenta criada para extrair arquivos .gim de  arquivos .pak dos jogos de PSP da Prototype.
Testado em: AIR, Planetarian Chiisana Hoshi no Yume

Unpack:
python3 unpack.py <input_PAK> <output_DIRECTORY>

Repack:
python3 pack.py <input_DIRECTORY> <output_PAK>


## Editando imagens .gim (PSP)

Esse método foi aplicado para a edição das imagens de AIR, e foi útil principalmente para lidar com as transparências.
Ainda não testamos, mas certamente essa técnica deve trabalhar com outros jogos de PSP da Prototype (Kanon, Planetarian, Clannad, Little Busters, etc.).

### Tools:
- GIM-Viewer (visualizados de arquivos gim)
- GimConv (converte gim para png e vice-versa)
- pngquant (otimiza o png para uso no psp e ativa a transparência)

Basicamente, o passo a passo é:

- Converter o arquivo gim para png
- Editar o png
- Passar o png editado no pngquant
- Converter o png para gim

1) Converter gim > png:
.\GimConv.exe .\17.gim -o .\17.png

2) Edite o png no seu software de imagens preferido
Os arquivos gim convertidos em png estarão no modo de cor indexado
Passe os arquivos png para rgb para poder usar transparência

3) Passe o png editado no pngquant
png256.bat <arquivo.png>

4) Converter png > gim:
.\GimConv.exe .\17.png .\17.gim -air

5) Devolva o arquivo para a pasta do game, faça o repack (se necessário) e teste no jogo.
