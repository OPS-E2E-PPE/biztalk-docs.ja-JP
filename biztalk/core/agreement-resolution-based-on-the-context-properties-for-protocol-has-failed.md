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
ms.openlocfilehash: a2cac1ea6e940385fceac541df96582f93eb058e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008171"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a>プロトコルに対するコンテキスト プロパティに基づくアグリーメントの解決が失敗しました
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
 このエラー/警告/情報イベントは、BizTalk Server がユーザーによって指定されたコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、アグリーメントの解決が実行されるように、BizTalk メッセージの一部としてコンテキスト プロパティを指定します。