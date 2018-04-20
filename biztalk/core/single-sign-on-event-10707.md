---
title: 'シングル サインオン: イベント 10707 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10707"></a>シングル サインオン: イベント 10707
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10707|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_NO_APP_SYNC|  
|メッセージ テキスト|このアダプターのパスワード同期フラグは、パスワード同期を許可し、グローバル フラグと一致している必要があります。 アダプター フラグとグローバル フラグを確認してください。%r<br /><br /> アダプター: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、このアダプターのパスワード同期フラグが、パスワード同期を許可し、グローバル フラグと一致している必要があることを示します。  
  
 パスワード同期アダプターのパスワード同期は、2 つのフラグによって制御されます。1 つは外部システムへのパスワードの送信を許可するフラグ (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) で、もう 1 つは外部システムからのパスワードの受信を許可するフラグ (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB) です。 パスワード同期を正常に実行するには、"グローバル フラグ" と特定のアダプター フラグの両方でこれらを設定する必要があります。 この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、これらのフラグのいずれかが、グローバル フラグおよびアダプター フラグの両方で設定されていない場合に発行されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:  
  
-   SSO 管理 MMC スナップインを使用して (システム & #124 文字です。プロパティと #124 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。  
  
## <a name="more-info"></a>詳細
  
-   **エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)