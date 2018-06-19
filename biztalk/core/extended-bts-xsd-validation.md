---
title: 拡張された (BTS-XSD) 検証 |Microsoft ドキュメント
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
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245954"
---
# <a name="extended-bts-xsd-validation"></a>拡張された (BTS-XSD) 検証
EDI 受信パイプラインと EDI 送信パイプラインは、データ型が EDI データ型ではない要素を使用してスキーマがカスタマイズされている場合にのみ、拡張された検証を実行します。 これらの追加された要素は、EDI 検証では検証されず、拡張された検証の対象にもなりません。 拡張された検証には `System.Xml.XmlValidatingReader` が使用され、標準 XSD に定義可能なすべてのチェックが含まれます。  
  
 拡張された検証は、パーティに対して送受信するすべてのメッセージに構成できます。 選択してこれを行う、 **Extended Validation**のチェック ボックス、**検証**ページ (下にある、**トランザクション セットの設定**X12 または EDIFACT のいずれかのセクション) で、一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 拡張された検証を有効にするために、EDI 検証を有効にする必要はありません。同様に、EDI 検証を有効にするために、拡張された検証を有効にする必要はありません。  
  
 拡張された検証では、次のチェックが行われます。  
  
-   データ要素要件および使用可能な繰り返し  
  
-   列挙型  
  
-   データ要素の長さの検証 (最小/最大)  
  
> [!IMPORTANT]
>  EDI 送信側のバッチ メッセージの Extended Validation はサポートされません。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)