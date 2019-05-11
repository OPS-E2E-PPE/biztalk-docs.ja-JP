---
title: 管理パックをインポートする前に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28bd8cdbb520c5f2ee7f22cb0e2b035b32c44aa8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401303"
---
# <a name="before-you-import-the-management-pack"></a>管理パックをインポートする前に
ベスト プラクティスとしては、使用しているオペレーティング システム用の Windows Server 管理パックをインポートする必要があります。 インポートする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、次の操作を実行します。  
  
-   Operations Manager 2007 R2 または 2012 がインストールされていることを確認します。  
  
-   SCOM 管理者グループまたは SCOM 作成者グループのいずれかのメンバーがあります。 SCOM 管理サーバー上のローカル管理者では、すべての権限と、SCOM 管理者グループに与えられるアクセス許可があります。  
  
-   各 BizTalk server を管理する SCOM エージェントを展開することで、BizTalk サーバーを Operations Manager で管理対象コンピューターとして設定します。 SCOM エージェントの展開には、次のタスクが含まれます。  
  
    -   SCOM エージェントをインストールします。  
  
    -   BizTalk の SCOM エージェントのアカウントを作成します。  
  
    -   構成、**実行**アカウント。 次のグループには、実行アカウントを追加します。  
  
        -   BizTalk グループ。  
  
        -   BizTalk 管理者。  
  
        -   SSO 管理者。  
  
        -   SSO 関連管理者です。  
  
    -   監視を開始します。  
  
-   Operation Manager コンソールで管理されたコンピューターは正常な状態です。  
  
-   任意の必要な実行アカウントやプロファイルなど、設定する必要があるすべてのユーザー アカウントを構成します。 この管理パックには、エージェントごとに特定の資格情報を定義するには、「BizTalk Server 監視アカウント」と「BizTalk Server 検出アカウント」という名前の実行プロファイルが含まれています。 管理パックをインポートした後に、一部のエージェントに対してこの実行プロファイルを使用する必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [この管理パックのファイル](../technical-guides/files-in-this-management-pack.md)  
  
-   [推奨される追加の管理パック](../technical-guides/recommended-additional-management-packs.md)