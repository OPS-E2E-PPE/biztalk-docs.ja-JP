---
title: 'シングル サインオン: イベント 10678 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daa6639e361abf364e012ec9a4f19f049bbcd08f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270050"
---
# <a name="single-sign-on-event-10678"></a>シングル サインオン: イベント 10678
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10678|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PASSWORD_MISMATCH|  
|メッセージ テキスト|外部パスワードが変更されています。 アダプターによって指定された古いパスワードは、外部アカウントの既存のパスワードと一致しません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> 外部アカウント: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アダプターによって指定された古いパスワードが、外部アカウントの既存のパスワードと一致しないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の手順を実行します。  
  
-   このアダプターにどのアプリケーションが割り当てられていたかを確認し (イベント ログ メッセージに名前があります)、SSO 管理ツールを使用してこの外部アカウントの外部資格情報を設定します。 それらのアプリケーションのすべてに対して (指定されたアカウントに) 外部パスワードを設定する必要があります。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期](../core/password-synchronization2.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]