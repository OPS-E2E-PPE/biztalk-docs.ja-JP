---
title: 'シングル サインオン: イベント 10715 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24bf65f00d9ef915d585c91aa06900b96d4b44d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270850"
---
# <a name="single-sign-on-event-10715"></a>シングル サインオン: イベント 10715
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10715|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_NO_CREATE_ADAPTER|  
|メッセージ テキスト|アダプターを作成するには、クライアント ユーザーは SSO 管理者アカウントのメンバーである必要があります。%r<br /><br /> クライアント ユーザー: %1 %r<br /><br /> SSO 管理者: %2 %r<br /><br /> アダプター: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アダプターを作成するにはクライアント ユーザーが SSO 管理者アカウントのメンバーである必要があることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   SSO 管理者グループに属しているアカウントでログオンします。  
  
 詳細については、次のリソースを参照してください。  
  
-   [SSO ユーザー グループ](../core/sso-user-groups.md)