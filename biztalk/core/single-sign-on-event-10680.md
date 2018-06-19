---
title: 'シングル サインオン: イベント 10680 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd7b1804578e1b0880eaa564f68a24f0841280fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270682"
---
# <a name="single-sign-on-event-10680"></a>シングル サインオン: イベント 10680
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10680|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_GET_CREDS_FAILED|  
|メッセージ テキスト|既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを変更できませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> 外部アカウント: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを変更できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   外部資格情報を確認します。  
  
-   外部資格情報が有効ではない場合は、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。 関連付けられたすべてのアプリケーションにおいて、(特定のアカウントの) 外部パスワードを設定する必要があります。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期](../core/password-synchronization2.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]