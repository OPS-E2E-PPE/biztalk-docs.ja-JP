---
title: 'シングル サインオン: イベント 10585 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b4781628121edad8904130e546038698de03161
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271522"
---
# <a name="single-sign-on-event-10585"></a>シングル サインオン: イベント 10585
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10585|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_EXPIRED_TICKET_REDEEMED|  
|メッセージ テキスト|チケットのタイムアウト期間が経過した後に、チケットの引き換えが行われています。 このアプリケーションについてチケットのタイムアウトが無効になっているので、この処理は許可されます。%r<br /><br /> アプリケーション名: %1|  
  
## <a name="explanation"></a>説明  
 チケットのタイムアウトは有効または無効にすることができます。 この場合、タイムアウトが無効になっているので、チケットのタイムアウト期間が経過した後でも、チケットの引き換えが実行されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 タイムアウトが無効であることが想定されている場合、ユーザーの操作は必要ありません。 ただし、この特定のアプリケーションでタイムアウトが無効であったかどうかがわからない場合は、すぐにアプリケーションを調べてこれを許可することを確認します。