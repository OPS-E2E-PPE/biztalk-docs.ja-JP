---
title: TIBCO Rendezvous でのマッピングをメッセージ |Microsoft Docs
description: メッセージ フィールドと TIBCO Rendezvous の BizTalk アダプター内の XML へのメッセージ マッピング
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8d3b287bc1475227231301275500fca32e90da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326208"
---
# <a name="message-mapping-in-tibco-rendezvous"></a>TIBCO Rendezvous でのメッセージ マッピング
TIBCO Rendezvous メッセージはヘッダー情報とメッセージ フィールドのセットで構成されます。 ヘッダー情報は、メッセージ コンテキスト プロパティに直接マップされます。  
  
## <a name="message-field-elements"></a>メッセージ フィールドの要素  
 メッセージ フィールドは、次の要素で構成されます。  
  
|要素|説明|  
|-------------|-----------------|  
|**名前**|文字の文字列。 メッセージに一意であることはありません。|  
|**[Identifier]**|短整数。 メッセージに一意です。 暗黙的に 65535 までのメッセージ フィールドの数を制限します。 識別子のスコープは、メッセージ (またはサブ メッセージ) です。 同じ識別子をそれ自体が 2 つのサブのメッセージで使用できるメッセージに含まれるの一部です。|  
|**[値]**|メッセージ フィールドのデータ。|  
|**Count**|(配列) の場合は項目の数|  
|**型**|メッセージ フィールドの型。|  
  
### <a name="mapping-process"></a>マッピング プロセス  
 構造化 TIBCO Rendezvous メッセージは、次のように XML 要素にマップされます。  
  
-   **名前**要素名として使用されます。 TIBCO Rendezvous のフィールド名は、XML 要素名で使用するために無効な文字を含めることができます。 アダプターにより生成される文字の有効な XML と TIBCO Rendezvous 間のマッピングがメッセージを構造化します。  
  
-   **識別子**'id' 属性に格納されます。  
  
-   **値**要素の本体である文字列表記を含みます。  
  
-   **カウント**は無視されます。  
  
-   **型**情報は生成された要素の xsi:type 属性に配置されます。  
  
     詳細については、次を参照してください。 [Data Type Mapping for TIBCO rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)します。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)