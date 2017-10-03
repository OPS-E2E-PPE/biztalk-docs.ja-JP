---
title: "シングル サインオン: イベント 10596 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051fdf627edc3f560a8d02026207dc2fe5bb3533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10596"></a>シングル サインオン: イベント 10596
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10596|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_TICKET_USER_NOT_IN_GROUP|  
|メッセージ テキスト|チケットの発行対象のユーザーがアプリケーション ユーザー アカウントのメンバーではないため、チケットを引き換えることができません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> %2 のチケットの発行先: %r<br /><br /> アプリケーション ユーザー: %3|  
  
## <a name="explanation"></a>説明  
 チケットの発行対象のユーザーがアプリケーション ユーザー アカウントのメンバーではないため、チケットを引き換えることができません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーション ユーザー アカウントのメンバーであるユーザーにチケットを再発行します。