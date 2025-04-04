<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sushi Toshi | menu</title>
    <style>
        :root {
            --primary: #c82506; /* Red */
            --secondary: #f8e5d6; /* beige */
        }
        body {
            font-family: 'Noto Sans JP', sans-serif;
            background-color: var(--secondary);
            color: #333;
            margin: 0;
        }
        .header {
            background: var(--primary);
            color: white;
            padding: 25px 20px;
            text-align: center;
            position: relative;
        }
        .logo {
            font-size: 28px;
            letter-spacing: 2px;
            font-weight: 500;
        }
        .sushi-icon {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 24px;
        }
        .category {
            margin: 25px 15px;
        }
        .category-title {
            color: var(--primary);
            border-bottom: 2px solid var(--primary);
            padding-bottom: 5px;
            font-size: 20px;
            display: flex;
            align-items: center;
        }
        .category-title:before {
            content: "🍣";
            margin-right: 8px;
        }
        .item {
            background: white;
            margin: 15px 0;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(200, 37, 6, 0.1);
        }
        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .item-name {
            font-weight: 500;
            font-size: 18px;
        }
        .item-price {
            color: var(--primary);
            font-weight: bold;
        }
        .item-desc {
            color: #666;
            font-size: 14px;
            margin-top: 8px;
            line-height: 1.4;
        }
        .footer {
            text-align: center;
            padding: 20px;
            color: #888;
            font-size: 12px;
        }
        /* 手机横屏适配 */
        @media (max-width: 767px) and (orientation: landscape) {
            .category {
                display: inline-block;
                width: 45%;
                vertical-align: top;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500&display=swap" rel="stylesheet">
</head>
<body>
    <div class="header">
        <div class="logo">SUSHI TOSHI</div>
        <div class="sushi-icon">🍱</div>
    </div>

    <div id="Menu">
        <!-- SASHIMI -->
        <div class="category">
            <div class="category-title">SASHIMI</div>
        </div>
            
            <div class="item">
                <div class="item-header">
                    <div class="item-name">Salmon</div>
                </div>  
            <div class="item">
                <div class="item-header">
                    <div class="item-name">Tuna</div>
            </div>

        <!-- NIGIRI -->
        <div class="category">
            <div class="category-title">NIGIRI</div>
            
            <div class="item">
                <div class="item-header">
                    <div class="item-name">Salmon</div>
                </div>            
            <div class="item">
                <div class="item-header">
                    <div class="item-name">Tuna</div>            
        </div>

        <!-- 刺身 -->
        <div class="category">
            <div class="category-title">刺身拼盘</div>
            
            <div class="item">
                <div class="item-header">
                    <div class="item-name">特上刺身盛合</div>
                    <div class="item-price">¥198</div>
                </div>
                <div class="item-desc">金枪鱼大腹+北海道海胆+牡丹虾+三文鱼</div>
            </div>
        </div>
    </div>

    <div class="footer">
        © 2024 Sushi Toshi · 每日鲜鱼直送 · 营业时间 11:00-22:00
    </div>

    <script>
        // 交互增强脚本
        document.querySelectorAll('.category-title').forEach(title => {
            title.addEventListener('click', function() {
                const items = this.parentElement.querySelectorAll('.item');
                const isHidden = items[0].style.display === 'none';
                
                items.forEach(item => {
                    item.style.display = isHidden ? 'block' : 'none';
                });
                
                this.style.borderBottom = isHidden ? 
                    '2px solid var(--primary)' : '2px dashed var(--primary)';
            });
        });

        // 自动展开第一个分类
        document.querySelector('.category').querySelectorAll('.item')
            .forEach(item => item.style.display = 'block');
    </script>
</body>
</html>
