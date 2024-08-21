# Módulo 1

- É possível criar Layouts específicos para grupos de rotas criados dentro de app/
- Se criar uma pasta com () ao seu redor, a pasta não irá para a URL. 
Exemplo:
```
(auth)/
    sign-in/page.tsx
    sign-up/page.tsx
    layout.tsx
```
Dessa forma podemos criar um layout que será compartilhado entre as páginas internas, mas o auth não necessariamente precisa aparecer na URL
- Podemos receber mais de uma informação no parâmetro da rota se criarmos a pasta na forma de spread.
Exemplo:
```
product/
    [...data]/
        page.tsx
```
```
page.tsx/

interface ProductProps {
    params: {
        data: string[]
    }
}

export default function Product({ params }: ProductProps) {
    const [productId, size, color] = params.data

    return (
        <div>
            <p>Product: {productId}</p>
            <p>Size: {size}</p>
            <p>Color: {color}</p>
        </div>
    )
}
```
