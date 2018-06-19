---
title: 'シングル サインオン: イベント 10668 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eb3dd4d-04b5-4713-93c1-76af012d6920
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 006855842ea2d789290200d5c5a9692b6e046e8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271442"
---
# <a name="single-sign-on-event-10668"></a>シングル サインオン: イベント 10668
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10668|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_NO_OLD_WINDOWS_PASSWORD|  
|メッセージ テキスト|SSO データベースでこのアカウントの古い Windows パスワードを使用できないので、Windows パスワードを変更できません。%r<br /><br /> SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> Windows アカウント: %3|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO データベースでこのアカウントの古い Windows パスワードが使用できないので、パスワード同期で Windows パスワードを変更できないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   このアダプターに割り当てられているアプリケーション (イベント ログ メッセージ内の名前) を特定し、SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。 このようなアプリケーションのすべてにおいて、(特定の Windows アカウントの) 外部パスワードを設定する必要があります。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期](../core/password-synchronization2.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]