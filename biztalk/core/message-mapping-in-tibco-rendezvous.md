---
title: "TIBCO Rendezvous でのマッピングをメッセージ |Microsoft ドキュメント"
description: "メッセージ フィールドと TIBCO Rendezvous の BizTalk アダプター内の XML へのメッセージ マッピング"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="message-mapping-in-tibco-rendezvous"></a>TIBCO Rendezvous でのメッセージ マッピング
TIBCO Rendezvous メッセージは、ヘッダー情報と一連のメッセージ フィールドで構成されています。 ヘッダー情報は、メッセージ コンテキスト プロパティに直接マップされます。  
  
## <a name="message-field-elements"></a>メッセージ フィールドの要素  
 メッセージ フィールドは以下の要素で構成されています。  
  
|要素|Description|  
|-------------|-----------------|  
|**名前**|文字の文字列。 メッセージ内で一意である必要はありません。|  
|**[Identifier]**|短整数。 メッセージ内で一意です。 暗黙的に 65535 メッセージ フィールドの数を制限します。 識別子のスコープは、メッセージ (またはサブメッセージ) です。 同じメッセージに含まれる 2 つのサブメッセージで、同じ識別子を使用できます。|  
|**値**|メッセージ フィールドのデータ。|  
|**Count**|項目の数 (配列の場合)。|  
|**型**|メッセージ フィールドの種類。|  
  
### <a name="mapping-process"></a>マッピング プロセス  
 TIBCO Rendezvous の構造化されたメッセージは、以下のようにして XML 要素にマップされます。  
  
-   **名前**要素名として使用されます。 TIBCO Rendezvous のフィールド名には、XML の要素名では使用できない文字でも使用できます。 アダプターは、XML と TIBCO Rendezvous 構造化メッセージの間の有効な文字のマッピングを生成します。  
  
-   **識別子**'id' 属性に設定します。  
  
-   **値**要素の本体のある文字列表現が含まれています。  
  
-   **カウント**は無視されます。  
  
-   **型**情報は、生成される要素の xsi:type 属性に格納されます。  
  
     詳細については、次を参照してください。 [TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)