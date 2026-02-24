# Pizzaria-perfect
Site hospedagem
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perfect Pizzaria - Cardápio Digital</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        const CONFIG = {
            nome: "Perfect Pizzaria",
            slogan: "O sabor perfeito para você!",
            whatsappNumero: "61999969637",
            horarioFuncionamento: "Ter-Dom | 18h às 23h",
            endereco: "Rua Exemplo, 123 - Centro - Cidade/UF",
            corPrincipal: "#FF6B35",
            taxaEntrega: "Taxa de entrega: De acordo com sua quadra. Consulte um de nossos atendentes."
        };

        const BORDAS = [
            { id: 'sem_borda', nome: 'Sem Borda Recheada', preco: 0 },
            { id: 'catupiry', nome: 'Borda de Catupiry', preco: 10.00 },
            { id: 'cheddar', nome: 'Borda de Cheddar', preco: 10.00 },
            { id: 'chocolate', nome: 'Borda de Chocolate', preco: 14.00 },
            { id: 'cream_cheese', nome: 'Borda de Cream Cheese', preco: 20.00 }
        ];

        const CARDAPIO = [
            { id: 1, nome: "Mussarela", categoria: "pizzas", preco: 52.90, precoGrande: 55.90, descricao: "Molho, mussarela especial e orégano.", imagem: "https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=500&q=80", destaque: false },
            { id: 2, nome: "Duda", categoria: "pizzas", preco: 52.90, precoGrande: 55.90, descricao: "Molho, mussarela especial, azeitonas verdes, presunto desfiado.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 3, nome: "Marguerita", categoria: "pizzas", preco: 52.90, precoGrande: 55.90, descricao: "Molho, mussarela especial, tomate cereja, parmesão ralado, manjericão e orégano.", imagem: "https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=500&q=80", destaque: true },
            { id: 4, nome: "Calabresa", categoria: "pizzas", preco: 55.90, precoGrande: 59.90, descricao: "Molho, calabresa, mussarela especial, cebola, azeitona verde e orégano.", imagem: "https://images.unsplash.com/photo-1628840042765-356cda07504e?w=500&q=80", destaque: true },
            { id: 5, nome: "Calabacon", categoria: "pizzas", preco: 59.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, calabresa, bacon, cebola, azeitonas verdes e orégano.", imagem: "https://images.unsplash.com/photo-1604382354936-07c5d9983bd3?w=500&q=80", destaque: false },
            { id: 6, nome: "Portuguesa", categoria: "pizzas", preco: 52.90, precoGrande: 55.90, descricao: "Molho, mussarela especial, cebola, ovos ralado, presunto, azeitonas verdes e orégano.", imagem: "https://images.unsplash.com/photo-1604382354936-07c5d9983bd3?w=500&q=80", destaque: false },
            { id: 7, nome: "Moda", categoria: "pizzas", preco: 59.90, precoGrande: 65.90, descricao: "Molho, mussarela especial, calabresa, cebola, tomate, ovos ralado, presunto, azeitonas verdes e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 8, nome: "Quatro Queijos", categoria: "pizzas", preco: 62.90, precoGrande: 65.90, descricao: "Molho, catupiry, mussarela especial, gorgonzola, parmesão e orégano.", imagem: "https://images.unsplash.com/photo-1513104890138-7c749659a591?w=500&q=80", destaque: true },
            { id: 9, nome: "Atum", categoria: "pizzas", preco: 65.90, precoGrande: 72.90, descricao: "Molho, mussarela especial, cebola, atum e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 10, nome: "Frango Catupiry", categoria: "pizzas", preco: 55.90, precoGrande: 59.90, descricao: "Molho, frango desfiado regado com tempero, coberto com catupiry, mussarela e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            { id: 11, nome: "Fran/Bacon", categoria: "pizzas", preco: 59.90, precoGrande: 65.90, descricao: "Molho, mussarela especial, frango desfiado, bacon, tomate picado e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 12, nome: "Presubacon", categoria: "pizzas", preco: 59.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, cebola, bacon, presunto, azeitonas verdes e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 13, nome: "Bacon", categoria: "pizzas", preco: 62.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, bacon, cebola, azeitonas verdes e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            
            { id: 14, nome: "Frango/Cream", categoria: "chef", preco: 69.90, precoGrande: 75.90, descricao: "Molho, mussarela especial, frango, tomate, catupiry, alho frito, cream cheese, bacon e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            { id: 15, nome: "Pizzaiolo", categoria: "chef", preco: 69.90, precoGrande: 75.90, descricao: "Molho, mussarela especial, presunto, frango, alho frito, pimenta, cream cheese e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            { id: 16, nome: "Manú", categoria: "chef", preco: 59.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, peito de peru, maçã verde, catupiry, queijo parmesão e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 17, nome: "Lança Chamas", categoria: "chef", preco: 55.90, precoGrande: 65.90, descricao: "Molho, calabresa picante, mussarela especial, cebola e orégano.", imagem: "https://images.unsplash.com/photo-1628840042765-356cda07504e?w=500&q=80", destaque: false },
            { id: 18, nome: "São Paulo", categoria: "chef", preco: 59.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, peito de peru defumado, alho-poró, tomate cereja, manjericão, parmesão e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 19, nome: "Da Vovó", categoria: "chef", preco: 59.90, precoGrande: 69.90, descricao: "Molho, mussarela especial, frango desfiado regado com tempero da vovó, coberto com catupiry, parmesão e orégano.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            
            { id: 20, nome: "Doce de Leite", categoria: "doces", preco: 52.90, precoGrande: 55.90, descricao: "Mussarela e doce de leite.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 21, nome: "Chita", categoria: "doces", preco: 52.90, precoGrande: 55.90, descricao: "Mussarela especial, banana, canela e açúcar flambada com rum.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            { id: 22, nome: "Mineiro de Botas", categoria: "doces", preco: 65.90, precoGrande: 69.90, descricao: "Queijo coalho e goiabada gratinados no forno a lenha.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            { id: 23, nome: "Chita Gostosa", categoria: "doces", preco: 55.90, precoGrande: 59.90, descricao: "Banana, calda de chocolate e mussarela.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 24, nome: "Chocolate", categoria: "doces", preco: 55.90, precoGrande: 59.90, descricao: "Mussarela especial e chocolate.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: false },
            { id: 25, nome: "Chocolate c/ Morango", categoria: "doces", preco: 65.90, precoGrande: 69.90, descricao: "Mussarela especial, chocolate e morango.", imagem: "https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=500&q=80", destaque: true },
            
            { id: 26, nome: "Coca-Cola 2L", categoria: "bebidas", preco: 14.00, descricao: "Refrigerante Coca-Cola original, 2 litros.", imagem: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?w=500&q=80", destaque: false },
            { id: 27, nome: "Guaraná Antarctica 2L", categoria: "bebidas", preco: 14.00, descricao: "Refrigerante Guaraná Antarctica, 2 litros.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false },
            { id: 28, nome: "Fanta Laranja 2L", categoria: "bebidas", preco: 14.00, descricao: "Refrigerante Fanta Laranja, 2 litros.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false },
            { id: 29, nome: "Coca-Cola Lata", categoria: "bebidas", preco: 8.00, descricao: "Refrigerante Coca-Cola lata, 350ml.", imagem: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?w=500&q=80", destaque: false },
            { id: 30, nome: "Guaraná Antarctica Lata", categoria: "bebidas", preco: 8.00, descricao: "Refrigerante Guaraná Antarctica lata, 350ml.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false },
            { id: 31, nome: "Fanta Laranja Lata", categoria: "bebidas", preco: 8.00, descricao: "Refrigerante Fanta Laranja lata, 350ml.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false },
            { id: 32, nome: "Sprite Lata", categoria: "bebidas", preco: 8.00, descricao: "Refrigerante Sprite lata, 350ml.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false },
            { id: 33, nome: "Coca-Cola 600ml", categoria: "bebidas", preco: 10.00, descricao: "Refrigerante Coca-Cola, 600ml.", imagem: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?w=500&q=80", destaque: false },
            { id: 34, nome: "Guaraná Antarctica 600ml", categoria: "bebidas", preco: 10.00, descricao: "Refrigerante Guaraná Antarctica, 600ml.", imagem: "https://images.unsplash.com/photo-1625772299848-391b6a87d7b3?w=500&q=80", destaque: false }
        ];
    </script>

    <style>
        :root { --primary: #FF6B35; --primary-dark: #E85A04; --secondary: #2C3E50; --accent: #F1C40F; --bg: #0F0F0F; --surface: #1A1A1A; --surface-light: #252525; --text: #FFFFFF; --text-muted: #B0B0B0; --success: #27AE60; --shadow: 0 10px 40px rgba(0,0,0,0.5); --radius: 16px; }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Poppins', sans-serif; background: var(--bg); color: var(--text); overflow-x: hidden; }
        .header { background: linear-gradient(135deg, var(--surface) 0%, var(--bg) 100%); padding: 20px; position: fixed; width: 100%; top: 0; z-index: 1000; box-shadow: var(--shadow); border-bottom: 2px solid var(--primary); }
        .header-content { max-width: 1200px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; }
        .logo { display: flex; align-items: center; gap: 15px; }
        .logo-icon { width: 50px; height: 50px; background: var(--primary); border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 24px; animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.05); } }
        .logo-text h1 { font-size: 24px; font-weight: 800; background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .logo-text p { font-size: 12px; color: var(--text-muted); font-weight: 500; }
        .header-actions { display: flex; gap: 15px; align-items: center; }
        .cart-btn { position: relative; background: var(--surface-light); border: none; width: 50px; height: 50px; border-radius: 50%; color: var(--text); font-size: 20px; cursor: pointer; transition: all 0.3s; display: flex; align-items: center; justify-content: center; }
        .cart-btn:hover { background: var(--primary); transform: translateY(-2px); }
        .cart-count { position: absolute; top: -5px; right: -5px; background: var(--accent); color: var(--bg); font-size: 12px; font-weight: 700; width: 24px; height: 24px; border-radius: 50%; display: flex; align-items: center; justify-content: center; animation: bounce 0.5s; }
        @keyframes bounce { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.2); } }
        .hero { margin-top: 90px; padding: 40px 20px; text-align: center; background: radial-gradient(circle at center, var(--surface) 0%, var(--bg) 70%); }
        .hero h2 { font-size: 32px; font-weight: 700; margin-bottom: 10px; line-height: 1.2; }
        .hero h2 span { color: var(--primary); }
        .hero p { color: var(--text-muted); font-size: 16px; max-width: 500px; margin: 0 auto 30px; }
        .delivery-info { background: var(--surface); padding: 15px; border-radius: 12px; margin: 20px auto; max-width: 500px; border: 2px solid var(--accent); }
        .delivery-info i { color: var(--accent); margin-right: 8px; }
        .delivery-info p { color: var(--text); font-weight: 600; margin: 0; font-size: 14px; }
        .search-box { max-width: 500px; margin: 0 auto 30px; position: relative; }
        .search-box input { width: 100%; padding: 15px 50px 15px 20px; border: 2px solid var(--surface-light); border-radius: 50px; background: var(--surface); color: var(--text); font-size: 16px; font-family: 'Poppins', sans-serif; transition: all 0.3s; }
        .search-box input:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 20px rgba(255, 107, 53, 0.3); }
        .search-box i { position: absolute; right: 20px; top: 50%; transform: translateY(-50%); color: var(--text-muted); }
        .categories { display: flex; gap: 10px; overflow-x: auto; padding: 10px 20px; max-width: 1200px; margin: 0 auto; scrollbar-width: none; }
        .categories::-webkit-scrollbar { display: none; }
        .category-btn { flex-shrink: 0; padding: 12px 24px; border: 2px solid var(--surface-light); border-radius: 50px; background: var(--surface); color: var(--text-muted); font-family: 'Poppins', sans-serif; font-weight: 600; cursor: pointer; transition: all 0.3s; white-space: nowrap; }
        .category-btn:hover, .category-btn.active { background: var(--primary); border-color: var(--primary); color: white; transform: translateY(-2px); box-shadow: 0 5px 20px rgba(255, 107, 53, 0.4); }
        .menu-container { max-width: 1200px; margin: 40px auto; padding: 0 20px; }
        .section-title { font-size: 24px; font-weight: 700; margin-bottom: 20px; display: flex; align-items: center; gap: 10px; }
        .section-title::after { content: ''; flex: 1; height: 2px; background: linear-gradient(90deg, var(--surface-light) 0%, transparent 100%); margin-left: 10px; }
        .menu-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 25px; }
        .menu-item { background: var(--surface); border-radius: var(--radius); overflow: hidden; transition: all 0.3s; border: 1px solid var(--surface-light); position: relative; }
        .menu-item:hover { transform: translateY(-5px); box-shadow: var(--shadow); border-color: var(--primary); }
        .menu-item-image { width: 100%; height: 200px; object-fit: cover; position: relative; }
        .menu-item-badge { position: absolute; top: 15px; left: 15px; background: var(--accent); color: var(--bg); padding: 5px 12px; border-radius: 20px; font-size: 12px; font-weight: 700; text-transform: uppercase; }
        .menu-item-content { padding: 20px; }
        .menu-item-header { display: flex; justify-content: space-between; align-items: start; margin-bottom: 10px; }
        .menu-item-title { font-size: 18px; font-weight: 600; line-height: 1.3; }
        .menu-item-description { color: var(--text-muted); font-size: 14px; line-height: 1.5; margin-bottom: 15px; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
        
        .pizza-actions { display: flex; flex-direction: column; gap: 12px; margin-top: 15px; }
        .size-row { display: flex; justify-content: space-between; align-items: center; padding: 12px; background: var(--bg); border-radius: 10px; border: 1px solid var(--surface-light); }
        .size-info { display: flex; flex-direction: column; }
        .size-name { font-weight: 600; font-size: 14px; color: var(--text); }
        .size-price { font-weight: 700; color: var(--primary); font-size: 16px; }
        .btn-group { display: flex; gap: 8px; }
        .btn-add-size { padding: 8px 14px; background: var(--primary); border: none; border-radius: 8px; color: white; font-family: 'Poppins', sans-serif; font-weight: 600; cursor: pointer; transition: all 0.3s; font-size: 12px; display: flex; align-items: center; gap: 4px; }
        .btn-add-size:hover { background: var(--primary-dark); transform: scale(1.05); }
        .btn-half-half { padding: 8px 14px; background: var(--surface-light); border: 2px solid var(--primary); border-radius: 8px; color: var(--primary); font-family: 'Poppins', sans-serif; font-weight: 600; cursor: pointer; transition: all 0.3s; font-size: 12px; display: flex; align-items: center; gap: 4px; }
        .btn-half-half:hover { background: var(--primary); color: white; }
        
        .borda-section { margin: 20px 0; padding: 20px; background: var(--bg); border-radius: 12px; border: 2px solid var(--surface-light); }
        .borda-section h4 { color: var(--primary); margin-bottom: 15px; font-size: 16px; display: flex; align-items: center; gap: 8px; }
        .borda-options { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 10px; }
        .borda-option { padding: 12px; background: var(--surface); border: 2px solid var(--surface-light); border-radius: 10px; cursor: pointer; transition: all 0.3s; text-align: center; }
        .borda-option:hover { border-color: var(--primary); transform: translateY(-2px); }
        .borda-option.selected { border-color: var(--success); background: rgba(39, 174, 96, 0.1); }
        .borda-option .borda-name { font-weight: 600; font-size: 14px; display: block; margin-bottom: 4px; }
        .borda-option .borda-price { color: var(--primary); font-size: 13px; font-weight: 700; }
        .borda-option.selected .borda-price { color: var(--success); }
        
        .two-flavors-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.95); z-index: 5000; overflow-y: auto; }
        .two-flavors-modal.active { display: flex; align-items: center; justify-content: center; padding: 20px; }
        .two-flavors-content { background: var(--surface); border-radius: var(--radius); max-width: 900px; width: 100%; max-height: 95vh; overflow-y: auto; padding: 30px; border: 2px solid var(--primary); position: relative; }
        .two-flavors-header { text-align: center; margin-bottom: 25px; }
        .two-flavors-header h2 { color: var(--primary); font-size: 28px; margin-bottom: 10px; }
        .two-flavors-header p { color: var(--text-muted); }
        .selected-base { background: var(--bg); padding: 15px; border-radius: 12px; margin-bottom: 20px; border: 2px solid var(--primary); }
        .selected-base h4 { color: var(--primary); margin-bottom: 8px; font-size: 14px; text-transform: uppercase; }
        .selected-base p { font-weight: 600; font-size: 16px; }
        .flavors-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 15px; margin-bottom: 25px; max-height: 300px; overflow-y: auto; padding-right: 10px; }
        .flavor-option { background: var(--bg); padding: 15px; border-radius: 10px; border: 2px solid var(--surface-light); cursor: pointer; transition: all 0.3s; }
        .flavor-option:hover { border-color: var(--primary); transform: translateY(-2px); }
        .flavor-option.selected { border-color: var(--success); background: rgba(39, 174, 96, 0.1); }
        .flavor-option.disabled { opacity: 0.5; cursor: not-allowed; pointer-events: none; }
        .flavor-option h4 { font-size: 14px; margin-bottom: 5px; }
        .flavor-option p { font-size: 12px; color: var(--text-muted); margin-bottom: 8px; }
        .flavor-option .price { color: var(--primary); font-weight: 700; font-size: 14px; }
        .two-flavors-summary { background: var(--bg); padding: 20px; border-radius: 12px; margin: 20px 0; text-align: center; border: 2px solid var(--success); }
        .two-flavors-summary h3 { margin-bottom: 10px; color: var(--text-muted); font-size: 14px; }
        .two-flavors-summary .final-price { font-size: 32px; color: var(--success); font-weight: 800; }
        .two-flavors-summary .calculation { font-size: 14px; color: var(--text-muted); margin-top: 5px; }
        .two-flavors-summary .rule { font-size: 12px; color: var(--accent); margin-top: 8px; font-weight: 600; }
        .two-flavors-buttons { display: flex; gap: 15px; margin-top: 20px; }
        .two-flavors-buttons button { flex: 1; padding: 15px; border: none; border-radius: 12px; font-family: 'Poppins', sans-serif; font-weight: 700; cursor: pointer; transition: all 0.3s; }
        .btn-confirm-two { background: var(--success); color: white; }
        .btn-confirm-two:hover { background: #229954; }
        .btn-cancel-two { background: transparent; border: 2px solid var(--text-muted); color: var(--text-muted); }
        .btn-cancel-two:hover { border-color: #e74c3c; color: #e74c3c; }
        .close-two-flavors { position: absolute; top: 20px; right: 20px; width: 40px; height: 40px; background: var(--surface-light); border: none; border-radius: 50%; color: var(--text); font-size: 20px; cursor: pointer; transition: all 0.3s; }
        .close-two-flavors:hover { background: #e74c3c; color: white; }
        
        .cart-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); backdrop-filter: blur(5px); z-index: 2000; opacity: 0; visibility: hidden; transition: all 0.3s; }
        .cart-overlay.active { opacity: 1; visibility: visible; }
        .cart-sidebar { position: fixed; top: 0; right: -100%; width: 100%; max-width: 450px; height: 100%; background: var(--surface); z-index: 2001; transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1); display: flex; flex-direction: column; }
        .cart-sidebar.active { right: 0; }
        .cart-header { padding: 25px; border-bottom: 1px solid var(--surface-light); display: flex; justify-content: space-between; align-items: center; }
        .cart-header h3 { font-size: 20px; display: flex; align-items: center; gap: 10px; }
        .close-cart { background: none; border: none; color: var(--text); font-size: 24px; cursor: pointer; width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; transition: all 0.3s; }
        .close-cart:hover { background: var(--surface-light); }
        .cart-items { flex: 1; overflow-y: auto; padding: 20px; }
        .cart-empty { text-align: center; padding: 60px 20px; color: var(--text-muted); }
        .cart-empty i { font-size: 64px; margin-bottom: 20px; opacity: 0.5; }
        .cart-item { display: flex; gap: 15px; padding: 15px; background: var(--bg); border-radius: 12px; margin-bottom: 15px; animation: slideIn 0.3s; }
        @keyframes slideIn { from { opacity: 0; transform: translateX(20px); } to { opacity: 1; transform: translateX(0); } }
        .cart-item-image { width: 80px; height: 80px; border-radius: 10px; object-fit: cover; }
        .cart-item-details { flex: 1; }
        .cart-item-title { font-weight: 600; margin-bottom: 5px; font-size: 14px; }
        .cart-item-flavors { font-size: 12px; color: var(--text-muted); margin-bottom: 3px; font-style: italic; }
        .cart-item-size { font-size: 11px; color: var(--accent); margin-bottom: 3px; font-weight: 500; }
        .cart-item-borda { font-size: 11px; color: var(--primary); margin-bottom: 3px; }
        .cart-item-price { color: var(--primary); font-weight: 700; font-size: 16px; }
        .cart-item-actions { display: flex; align-items: center; gap: 10px; margin-top: 10px; }
        .qty-btn { width: 30px; height: 30px; border: 1px solid var(--surface-light); background: var(--surface); color: var(--text); border-radius: 8px; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: all 0.2s; }
        .qty-btn:hover { background: var(--primary); border-color: var(--primary); }
        .cart-item-qty { font-weight: 600; min-width: 20px; text-align: center; }
        .remove-item { margin-left: auto; color: #e74c3c; background: none; border: none; cursor: pointer; font-size: 16px; padding: 5px; }
        .cart-footer { padding: 25px; border-top: 1px solid var(--surface-light); background: var(--bg); }
        .cart-total { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; font-size: 20px; }
        .cart-total span:last-child { font-weight: 700; color: var(--primary); font-size: 24px; }
        .delivery-fee-notice { background: var(--surface-light); padding: 12px; border-radius: 8px; margin-bottom: 15px; text-align: center; font-size: 13px; color: var(--accent); border: 1px solid var(--accent); }
        .btn-checkout { width: 100%; padding: 18px; background: var(--success); border: none; border-radius: 12px; color: white; font-family: 'Poppins', sans-serif; font-size: 16px; font-weight: 700; cursor: pointer; transition: all 0.3s; display: flex; align-items: center; justify-content: center; gap: 10px; }
        .btn-checkout:hover { background: #229954; transform: translateY(-2px); box-shadow: 0 5px 20px rgba(39, 174, 96, 0.4); }
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); backdrop-filter: blur(10px); z-index: 3000; opacity: 0; visibility: hidden; transition: all 0.3s; display: flex; align-items: center; justify-content: center; padding: 20px; }
        .modal-overlay.active { opacity: 1; visibility: visible; }
        .modal-content { background: var(--surface); border-radius: var(--radius); max-width: 600px; width: 100%; max-height: 90vh; overflow-y: auto; position: relative; transform: scale(0.9); transition: all 0.3s; }
        .modal-overlay.active .modal-content { transform: scale(1); }
        .modal-close { position: absolute; top: 20px; right: 20px; width: 40px; height: 40px; background: rgba(0,0,0,0.5); border: none; border-radius: 50%; color: white; font-size: 20px; cursor: pointer; z-index: 10; transition: all 0.3s; }
        .modal-close:hover { background: var(--primary); transform: rotate(90deg); }
        .modal-image { width: 100%; height: 300px; object-fit: cover; }
        .modal-body { padding: 30px; }
        .modal-title { font-size: 28px; font-weight: 700; margin-bottom: 10px; }
        .modal-price { font-size: 32px; color: var(--primary); font-weight: 800; margin-bottom: 20px; }
        .modal-description { color: var(--text-muted); line-height: 1.8; margin-bottom: 25px; font-size: 16px; }
        .observation-box { margin-bottom: 25px; }
        .observation-box label { display: block; margin-bottom: 10px; font-weight: 600; color: var(--text-muted); }
        .observation-box textarea { width: 100%; padding: 15px; border: 2px solid var(--surface-light); border-radius: 12px; background: var(--bg); color: var(--text); font-family: 'Poppins', sans-serif; resize: vertical; min-height: 100px; }
        .observation-box textarea:focus { outline: none; border-color: var(--primary); }
        .modal-add-btn { width: 100%; padding: 18px; background: var(--primary); border: none; border-radius: 12px; color: white; font-family: 'Poppins', sans-serif; font-size: 18px; font-weight: 700; cursor: pointer; transition: all 0.3s; }
        .modal-add-btn:hover { background: var(--primary-dark); }
        .confirmacao-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.95); z-index: 4000; opacity: 0; visibility: hidden; transition: all 0.3s; display: flex; align-items: center; justify-content: center; padding: 20px; }
        .confirmacao-overlay.active { opacity: 1; visibility: visible; }
        .confirmacao-box { background: var(--surface); border-radius: var(--radius); max-width: 500px; width: 100%; padding: 30px; text-align: center; border: 2px solid var(--primary); max-height: 90vh; overflow-y: auto; }
        .confirmacao-box h2 { color: var(--primary); margin-bottom: 20px; font-size: 24px; }
        .confirmacao-box .pedido-resumo { background: var(--bg); padding: 20px; border-radius: 12px; margin: 20px 0; text-align: left; max-height: 300px; overflow-y: auto; }
        .confirmacao-box .pedido-item { display: flex; justify-content: space-between; margin-bottom: 10px; padding-bottom: 10px; border-bottom: 1px solid var(--surface-light); }
        .confirmacao-box .pedido-item:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
        .confirmacao-box .pedido-total { font-size: 20px; font-weight: 700; color: var(--primary); margin-top: 15px; padding-top: 15px; border-top: 2px solid var(--primary); }
        .btn-confirmar { width: 100%; padding: 18px; background: var(--success); border: none; border-radius: 12px; color: white; font-family: 'Poppins', sans-serif; font-size: 18px; font-weight: 700; cursor: pointer; margin-top: 20px; display: flex; align-items: center; justify-content: center; gap: 10px; }
        .btn-confirmar:hover { background: #229954; }
        .btn-cancelar { width: 100%; padding: 15px; background: transparent; border: 2px solid var(--text-muted); border-radius: 12px; color: var(--text-muted); font-family: 'Poppins', sans-serif; font-size: 16px; font-weight: 600; cursor: pointer; margin-top: 10px; }
        .btn-cancelar:hover { border-color: #e74c3c; color: #e74c3c; }
        .footer { background: var(--surface); padding: 40px 20px; text-align: center; border-top: 1px solid var(--surface-light); margin-top: 60px; }
        .footer p { color: var(--text-muted); margin-bottom: 15px; }
        .social-links { display: flex; justify-content: center; gap: 20px; margin-top: 20px; }
        .social-links a { width: 45px; height: 45px; background: var(--surface-light); border-radius: 50%; display: flex; align-items: center; justify-content: center; color: var(--text); font-size: 20px; transition: all 0.3s; text-decoration: none; }
        .social-links a:hover { background: var(--primary); transform: translateY(-3px); }
        
        .endereco-box { background: var(--bg); padding: 20px; border-radius: 12px; margin: 20px 0; text-align: left; border: 2px solid var(--surface-light); }
        .endereco-box label { display: block; margin-bottom: 10px; font-weight: 600; color: var(--text); display: flex; align-items: center; gap: 8px; }
        .endereco-box label i { color: var(--primary); }
        .endereco-box input { width: 100%; padding: 15px; border: 2px solid var(--surface-light); border-radius: 10px; background: var(--surface); color: var(--text); font-family: 'Poppins', sans-serif; font-size: 15px; transition: all 0.3s; }
        .endereco-box input:focus { outline: none; border-color: var(--primary); box-shadow: 0 0 0 3px rgba(255, 107, 53, 0.1); }
        .endereco-box small { display: block; margin-top: 8px; color: var(--text-muted); font-size: 12px; }
        .endereco-obrigatorio { color: #e74c3c; font-size: 12px; margin-left: 5px; }
        
        @media (max-width: 768px) { 
            .hero h2 { font-size: 24px; } 
            .menu-grid { grid-template-columns: 1fr; } 
            .cart-sidebar { max-width: 100%; } 
            .confirmacao-box { padding: 20px; } 
            .flavors-grid { grid-template-columns: 1fr; }
            .two-flavors-content { padding: 20px; }
            .borda-options { grid-template-columns: 1fr; }
        }
        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: var(--bg); }
        ::-webkit-scrollbar-thumb { background: var(--surface-light); border-radius: 5px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--primary); }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-content">
            <div class="logo">
                <div class="logo-icon">🍕</div>
                <div class="logo-text">
                    <h1 id="configNome">PERFECT PIZZARIA</h1>
                    <p id="configSlogan">O sabor perfeito para você!</p>
                </div>
            </div>
            <div class="header-actions">
                <button class="cart-btn" onclick="toggleCart()">
                    <i class="fas fa-shopping-bag"></i>
                    <span class="cart-count" id="cartCount" style="display: none;">0</span>
                </button>
            </div>
        </div>
    </header>

    <section class="hero">
        <h2>A Melhor Pizza da <span>Cidade</span></h2>
        <p>Ingredientes selecionados, massa artesanal e muito sabor. Escolha sua borda favorita!</p>
        
        <div class="delivery-info">
            <i class="fas fa-motorcycle"></i>
            <p id="deliveryText">Taxa de entrega: De acordo com sua quadra. Consulte um de nossos atendentes.</p>
        </div>
        
        <div class="search-box">
            <input type="text" id="searchInput" placeholder="Buscar no cardápio..." onkeyup="filterItems()">
            <i class="fas fa-search"></i>
        </div>
    </section>

    <div class="categories" id="categories">
        <button class="category-btn active" onclick="filterCategory('todos')">Todos</button>
        <button class="category-btn" onclick="filterCategory('pizzas')">Pizzas Tradicionais</button>
        <button class="category-btn" onclick="filterCategory('chef')">👨‍🍳 Pizzas Chef</button>
        <button class="category-btn" onclick="filterCategory('doces')">🍫 Pizzas Doces</button>
        <button class="category-btn" onclick="filterCategory('bebidas')">Bebidas</button>
    </div>

    <div class="menu-container">
        <h3 class="section-title" id="sectionTitle">🍕 Cardápio Completo</h3>
        <div class="menu-grid" id="menuGrid"></div>
    </div>

    <div class="two-flavors-modal" id="twoFlavorsModal">
        <div class="two-flavors-content">
            <button class="close-two-flavors" onclick="closeTwoFlavorsModal()"><i class="fas fa-times"></i></button>
            <div class="two-flavors-header">
                <h2><i class="fas fa-adjust"></i> Escolha 2 Sabores</h2>
                <p>Meia a meia sai pelo valor do sabor mais caro</p>
            </div>
            
            <div class="selected-base" id="selectedBase">
                <h4><i class="fas fa-pizza-slice"></i> Primeiro Sabor Selecionado</h4>
                <p id="baseFlavorName">-</p>
                <small id="baseFlavorDetails" style="color: var(--text-muted);"></small>
            </div>
            
            <h3 style="margin-bottom: 15px; font-size: 18px;">Escolha o segundo sabor:</h3>
            <div class="flavors-grid" id="flavorsGrid"></div>
            
            <div class="borda-section" id="bordaSectionTwoFlavors">
                <h4><i class="fas fa-circle-notch"></i> Escolha a Borda</h4>
                <div class="borda-options" id="bordaOptionsTwoFlavors"></div>
            </div>
            
            <div class="two-flavors-summary" id="twoFlavorsSummary" style="display: none;">
                <h3>Preço Final</h3>
                <div class="final-price" id="finalPrice">R$ 0,00</div>
                <div class="calculation" id="priceCalculation"></div>
                <div class="rule">⚡ Meia a meia: valor do sabor mais caro + borda</div>
            </div>
            
            <div class="two-flavors-buttons">
                <button class="btn-confirm-two" id="btnConfirmTwo" onclick="confirmTwoFlavors()" disabled>
                    <i class="fas fa-check"></i> Adicionar ao Pedido
                </button>
                <button class="btn-cancel-two" onclick="closeTwoFlavorsModal()">
                    <i class="fas fa-times"></i> Cancelar
                </button>
            </div>
        </div>
    </div>

    <div class="cart-overlay" id="cartOverlay" onclick="toggleCart()"></div>
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-bag"></i> Seu Pedido</h3>
            <button class="close-cart" onclick="toggleCart()"><i class="fas fa-times"></i></button>
        </div>
        <div class="cart-items" id="cartItems">
            <div class="cart-empty">
                <i class="fas fa-shopping-basket"></i>
                <p>Seu carrinho está vazio</p>
                <small>Adicione itens do cardápio</small>
            </div>
        </div>
        <div class="cart-footer" id="cartFooter" style="display: none;">
            <div class="delivery-fee-notice">
                <i class="fas fa-info-circle"></i> Taxa de entrega: Consulte valor com nossos atendentes
            </div>
            <div class="cart-total"><span>Total:</span><span id="cartTotal">R$ 0,00</span></div>
            <button class="btn-checkout" onclick="mostrarConfirmacao()">
                <i class="fab fa-whatsapp"></i> Finalizar Pedido
            </button>
        </div>
    </div>

    <div class="modal-overlay" id="productModal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal()"><i class="fas fa-times"></i></button>
            <img src="" alt="" class="modal-image" id="modalImage">
            <div class="modal-body">
                <h2 class="modal-title" id="modalTitle"></h2>
                <div class="modal-price" id="modalPrice"></div>
                <p class="modal-description" id="modalDescription"></p>
                
                <div class="borda-section" id="bordaSectionSimple">
                    <h4><i class="fas fa-circle-notch"></i> Escolha a Borda</h4>
                    <div class="borda-options" id="bordaOptionsSimple"></div>
                </div>
                
                <div class="observation-box">
                    <label>Observações (opcional):</label>
                    <textarea id="modalObs" placeholder="Ex: Sem cebola, bem passada, trocar refri..."></textarea>
                </div>
                <button class="modal-add-btn" onclick="addToCartFromModal()">
                    <i class="fas fa-plus"></i> Adicionar ao Pedido
                </button>
            </div>
        </div>
    </div>

    <div class="confirmacao-overlay" id="confirmacaoOverlay">
        <div class="confirmacao-box">
            <h2><i class="fab fa-whatsapp"></i> Confirmar Pedido</h2>
            <p style="color: var(--text-muted); margin-bottom: 20px;">Revise seu pedido antes de enviar:</p>
            <div class="pedido-resumo" id="pedidoResumo"></div>
            
            <div style="background: var(--bg); padding: 15px; border-radius: 10px; margin: 15px 0; border: 2px solid var(--accent);">
                <p style="color: var(--accent); font-weight: 600; margin: 0; font-size: 14px;">
                    <i class="fas fa-motorcycle"></i> Taxa de entrega: De acordo com sua quadra. Consulte um de nossos atendentes.
                </p>
            </div>
            
 
