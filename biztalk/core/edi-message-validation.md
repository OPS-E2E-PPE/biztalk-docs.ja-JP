---
title: EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ee189ccd827c72fd177d65eaa49461e2287538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350360"
---
# <a name="edi-message-validation"></a>EDI メッセージの検証
EDI データは自己記述型タグ) (なし、区切られたファイルとして送信し、エンコードの規則がコピー先のアプリケーションが正常に解析およびダウン ストリーム処理の情報を利用することであることを確認する厳密な書式規則を適用するためです。  
  
 EDI 受信パイプラインと EDI 送信パイプライン Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 は、一連の検証を実行します。 いくつかは常に実行します。他のユーザーは、アグリーメントでプロパティを有効にした場合、または、スキーマ内で実行されます。 検証を構成する方法の詳細については、次を参照してください。 [、EDI インターチェンジが構成されているの検証方法](../core/how-validation-of-an-edi-interchange-is-configured.md)します。  
  
 EDI インターチェンジの検証には、次のトピックで説明したようにいくつかの異なる種類検証にはが含まれます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI インターチェンジの検証を構成する方法](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [EDI 構造の検証](../core/edi-structural-validation.md)  
  
-   [アグリーメントのプロパティの検証](../core/agreement-properties-validation.md)  
  
-   [EDI の種類 (データ要素) の検証](../core/edi-type-data-element-validation.md)  
  
-   [拡張された (BTS-XSD) 検証](../core/extended-bts-xsd-validation.md)  
  
-   [スキーマの検証](../core/schema-validation2.md)  
  
-   [クロスフィールド/セグメント検証](../core/cross-field-segment-validation.md)