---
title: "EDI メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-validation"></a>EDI メッセージの検証
EDI データは、自己記述型タグを持たない区切られたファイルとして送信されます。そのため、エンコーディング規則は厳密な書式規則を適用して、送信先アプリケーションが下流の処理で情報を正常に解析および利用できるようにします。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 の EDI 受信パイプラインと EDI 送信パイプラインは、一連の検証を実行します。 これらの検証には、常に実行されるものと、アグリーメント プロパティまたはスキーマで有効にされた場合に実行されるものとがあります。 検証を構成する方法の詳細については、次を参照してください。 [、EDI インターチェンジが構成されているの検証方法](../core/how-validation-of-an-edi-interchange-is-configured.md)です。  
  
 EDI インターチェンジの検証には、以下のトピックで説明するように、さまざまな種類の検証が含まれます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI インターチェンジの検証を構成する方法](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [EDI 構造検証](../core/edi-structural-validation.md)  
  
-   [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)  
  
-   [EDI の種類 (データ要素) の検証](../core/edi-type-data-element-validation.md)  
  
-   [拡張 (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)  
  
-   [スキーマの検証](../core/schema-validation2.md)  
  
-   [クロス フィールド セグメント検証](../core/cross-field-segment-validation.md)