# Redirecionamento para o App

Este é um código HTML simples que realiza o redirecionamento do usuário para a loja de aplicativos correspondente (Google Play ou App Store) com base no dispositivo que ele está utilizando (Android ou iOS). Caso o dispositivo não seja nem Android nem iOS, o usuário será redirecionado para um link de fallback (pode ser um website ou outro recurso).

## Funcionalidade

1. **Detecta o Sistema Operacional**: Ao carregar a página, o script detecta automaticamente se o usuário está acessando a partir de um dispositivo Android ou iOS.
   
2. **Redireciona para a Loja de Aplicativos**: 
    - **Android**: Se o dispositivo for Android, o usuário será redirecionado para a [Google Play Store](https://play.google.com/store/apps/details?id=com.totvs.hr.mobile).
    - **iOS**: Se o dispositivo for iOS, o usuário será redirecionado para a [App Store](https://apps.apple.com/br/app/meu-rh/id1263940937).
   
3. **Fallback**: Se o dispositivo não for detectado como Android ou iOS, o usuário será redirecionado para um site de fallback (que pode ser configurado com o link desejado, no caso atual está definido como `https://www.seuwebsite.com`).

4. **Links Manuais**: Caso o redirecionamento automático não funcione, o usuário pode clicar nos links disponíveis para Android ou iOS para fazer o download manual do app.

## Como funciona?

### 1. **Detecção do Sistema Operacional**:
   O script usa a propriedade `navigator.userAgent` para verificar se o dispositivo do usuário é Android ou iOS. Dependendo da identificação, o redirecionamento é feito.

### 2. **Redirecionamento**:
   O redirecionamento é feito automaticamente assim que a página carrega, através do `window.location.href`, que leva o usuário para a URL da Play Store ou App Store correspondente.

### 3. **Página Fallback**:
   Caso o sistema operacional não seja identificado como Android ou iOS, o código redireciona o usuário para o URL `https://www.seuwebsite.com`, onde você pode incluir qualquer conteúdo alternativo.

### 4. **Links de Alternativa**:
   Se o redirecionamento automático não ocorrer, o código oferece links clicáveis para as versões Android e iOS do app.

## Como usar?

1. **Substitua as URLs**:
   - Substitua o link do Android (`https://play.google.com/store/apps/details?id=com.totvs.hr.mobile`) e o link do iOS (`https://apps.apple.com/br/app/meu-rh/id1263940937`) pelas URLs do seu próprio aplicativo.
   - Caso necessário, altere o link de fallback para o URL de seu site preferido.

2. **Integração no seu Site**:
   Basta incorporar este código HTML no seu site onde você deseja realizar o redirecionamento.

## Exemplo do Código

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Redirecionando para o App</title>
    <script type="text/javascript">
        window.onload = function() {
            var userAgent = navigator.userAgent || navigator.vendor || window.opera;
            if (/android/i.test(userAgent)) {
                window.location.href = "https://play.google.com/store/apps/details?id=com.totvs.hr.mobile";
            } else if (/iPad|iPhone|iPod/.test(userAgent)) {
                window.location.href = "https://apps.apple.com/br/app/meu-rh/id1263940937";
            } else {
                window.location.href = "https://www.seuwebsite.com";
            }
        };
    </script>
</head>
<body>
    <h1>Redirecionando...</h1>
    <p>Se o redirecionamento não ocorrer automaticamente, <a href="https://play.google.com/store/apps/details?id=com.totvs.hr.mobile">clique aqui para Android</a> ou <a href="https://apps.apple.com/br/app/meu-rh/id1263940937">aqui para iOS</a>.</p>
</body>
</html>
```

## Customizações

- **Personalizar o Texto**: Modifique o texto dentro da tag `<h1>` ou `<p>` para adequar à sua comunicação com o usuário.
  
- **Alterar o Estilo**: Se desejar, adicione CSS para personalizar o estilo da página.

## Contribuições

Se você deseja contribuir com melhorias, correções de bugs ou adicionar novas funcionalidades, fique à vontade para fazer um fork do repositório e enviar um pull request.



