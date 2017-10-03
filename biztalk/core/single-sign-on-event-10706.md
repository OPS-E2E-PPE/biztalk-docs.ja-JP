---
title: "シングル サインオン: イベント 10706 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5703c81d87376349561f644da558b8594cd51b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10706"></a>シングル サインオン: イベント 10706
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10706|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_NO_GLOBAL_SYNC|  
|メッセージ テキスト|グループ アダプターはグローバル フラグによってパスワード同期を許可される必要があります。 グローバル フラグを確認してください。%r<br /><br /> アダプタ: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、いずれのグローバル フラグも設定されていないことを示します。 いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグ: する SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可する SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もうです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   SSO 管理 MMC スナップインで、(システム (&) #124; を使用します。プロパティ & #124 です。オプション) またはコマンド ライン ツール`ssomanage –enable winsync/extsync`グローバル フラグを有効にします。  
  
## <a name="more-info"></a>詳細
  
-   **エンタープライズ シングル サインオン フラグ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)