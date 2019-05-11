---
title: メッセージの種類は、アグリーメントの一部として許可されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d5bb18ad9a46150b45d6994182ad18eb4fa564
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394545"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>メッセージの種類は、アグリーメントの一部として使用できません。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                          TransactionSetNotAllowedDescription                           |
|  メッセージ テキスト   |               メッセージの種類{0}は、アグリーメントの一部として許可されていません。                |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がアグリーメントの一部として、ドキュメントのメッセージの種類が許可されていないため、ドキュメントを処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージの種類は許可されているし、アグリーメントの一部として許可されていませんが参照してください。