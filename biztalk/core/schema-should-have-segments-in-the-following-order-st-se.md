---
title: スキーマは、ST の次の順序でセグメントをある必要があります.SE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b975f28221941ef84f0683fae1597816640d48a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396902"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a>スキーマは、ST の次の順序でセグメントをある必要があります.SE
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                    SchemaCode116ETransactionSetSchemaStSeOutOfOrder                    |
|  メッセージ テキスト   |             スキーマは、ST の次の順序でセグメントをある必要があります.SE              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、カスタム ドキュメント スキーマが無効である、正しい順序でヘッダーとトレーラーがないためにことを示します。 BizTalk Server は、スキーマが展開されているときに、この検証を実行します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ヘッダーとトレーラーが正しい順番とし、スキーマを再配置できるように、カスタマイズされたドキュメント スキーマを変更します。