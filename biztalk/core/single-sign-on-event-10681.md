---
title: 'シングル サインオン: イベント 10681 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0f1b6c27f3e77220d4615da1c0b5bb343344de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272042"
---
# <a name="single-sign-on-event-10681"></a>シングル サインオン: イベント 10681
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10681|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE|  
|メッセージ テキスト|外部パスワードが変更されています。 1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードは変更されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> Windows アカウント: %3|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードが変更されなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   システムおよびアプリケーション イベント ログで関連するイベントを確認してください。  
  
-   SSO 管理ツールを使用してアダプターの構成を確認します。  
  
-   外部システムを確認します。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期](../core/password-synchronization2.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]