---
title: 拡張された (BTS-XSD) 検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f102e1d5a182b729af164a83efa8f20be49ba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345920"
---
# <a name="extended-bts-xsd-validation"></a>拡張された (BTS-XSD) 検証
EDI 受信パイプラインと EDI 送信パイプラインがデータ型が EDI データ型ではない要素を持つスキーマがカスタマイズされている場合にのみ、拡張された検証を実行します。 これらの追加要素は、拡張された検証の対象に、EDI 検証では検証されません。 検証の使用を拡張`System.Xml.XmlValidatingReader`標準 XSD に定義できるすべてのチェックが含まれています。  
  
 パーティとの間のすべてのメッセージの extended validation を構成します。 選択してこれを行う、 **Extended Validation**でチェック ボックスをオン、**検証**ページ (下、**トランザクション セットの設定**X12 または EDIFACT のいずれかのセクション) で、一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 EDI の検証を有効にしなくても拡張機能の検証を有効にすることができますまたはその逆です。  
  
 拡張された検証は、次のチェックで構成されます。  
  
-   データ要素の要件と使用可能な繰り返し  
  
-   列挙  
  
-   データ要素の長さの検証 (最小/最大)。  
  
> [!IMPORTANT]
>  EDI 送信側バッチ処理されたメッセージの extended Validation はサポートされていません。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)