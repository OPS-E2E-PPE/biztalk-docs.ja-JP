---
title: アグリーメントの解決は、プロトコルのコンテキスト プロパティに基づく |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5cb408e59f6817be9aa06f94d3b83d90f07c494
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359921"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a>アグリーメントのコンテキスト プロパティ プロトコルに基づく解決が失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                    AgreementResolutionContextPropertiesLookupFailed                    |
|  メッセージ テキスト   |   コンテキスト プロパティに基づくアグリーメント解決{0}プロトコルが失敗しました。    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server で、顧客が用意されているコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、コンテキスト プロパティの BizTalk メッセージの一部としてでの指定は、アグリーメントの解決が実行されるようにしてください。