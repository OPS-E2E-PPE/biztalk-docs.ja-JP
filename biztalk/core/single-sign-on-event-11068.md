---
title: シングル サインオン:イベント 11068 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 634fdcb87698628e2a579028ea8fad11ac035d27
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530771"
---
# <a name="single-sign-on-event-11068"></a>シングル サインオン:イベント 11068
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                      エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    イベント ID     |                                                                                11068                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                                |
|    コンポーネント    |                                                                                 なし                                                                                 |
|  シンボル名  |                                                          SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE                                                          |
|  メッセージ テキスト   | 参照サーバーのアクセスが拒否されました。 この SSO サーバーは、現在、リモート参照を許可するように構成されていません。 'ssoconfig -remoteLookup yes' または SSO 管理 MMC を使用してください。%r |
  
## <a name="explanation"></a>説明  
 ENTSSO サーバーがリモート参照を許可するように構成されていないため、参照サーバー アクセスが拒否されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 リモートの検索を可能にする、**サーバー スナップイン**、**詳細**] タブで [**リモート検索を許可する**します。  
  
 詳細については、次を参照してください。[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)します。