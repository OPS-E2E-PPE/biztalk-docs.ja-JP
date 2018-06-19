---
title: BizTalk マッパーの有効な XSLT エンコードの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- grid properties
- Code Page property
- XSLT Encoding property [grid pages]
- Schema node
- XSLT, encoding types [BizTalk Mapper]
- BizTalk Mapper, XSLT encoding
ms.assetid: 922b46cb-7bc8-4267-bf52-e5f0262b8da1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e8b69de5c60a1701f0989f725d9225633d38ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288018"
---
# <a name="valid-biztalk-mapper-xslt-encoding-types"></a>BizTalk マッパーでの有効な XSLT エンコードの種類
BizTalk マッパーは、各種の XSLT (Extensible Stylesheet Language Transformations) エンコードをサポートしています。 使用する、 **XSLT エンコード**グリッド プロパティをエンコードの種類を必要に応じて、XSLT を設定します。 次の一覧に関連付けられているドロップダウン リストで使用できるエンコード形式を示しています、 **XSLT エンコード**グリッドのプロパティ。  
  
-   なし  
  
-   アラビア語 (windows-1256)  
  
-   バルト語 (windows-1257)  
  
-   中央ヨーロッパ言語 (windows-1250)  
  
-   中国語 (GB18030)  
  
-   キリル語 (windows-1251)  
  
-   ギリシャ語 (windows-1253)  
  
-   ヘブライ語 (windows-1255)  
  
-   日本語 (Shift_JIS)  
  
-   韓国語 (ks_c_5601-1987)  
  
-   リトル エンディアン Unicode (UTF-16)  
  
-   簡体字中国語 (GBK)  
  
-   タイ語 (windows-874)  
  
-   繁体字中国語 (Big5)  
  
-   トルコ語 (windows-1254)  
  
-   UTF-8  
  
-   ベトナム語 (windows-1258)  
  
-   西ヨーロッパ言語 (windows-1252)  
  
 必要なエンコードがこの一覧に含まれていない場合、別のエンコード値を入力できます。 BizTalk マッパーはその値のテストを行わないので、適切な値を入力していることを確認してください。  
  
> [!NOTE]
>  **コード ページ**のプロパティ、**スキーマ**ノードがマップで使用するスキーマのエンコード形式を定義します。 構成するのには**コード ページ**プロパティ、スキーマを BizTalk エディターで開きし、値を指定、**コード ページ**プロパティです。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)