---
title: 管理パックをインポートする前に |Microsoft ドキュメント
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
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299450"
---
# <a name="before-you-import-the-management-pack"></a>管理パックをインポートする前に
ベスト プラクティスとしてを使用しているオペレーティング システム用の Windows Server 管理パックをインポートする必要があります。 インポートする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、次の操作を実行します。  
  
-   Operations Manager 2007 R2 または 2012 がインストールされていることを確認します。  
  
-   SCOM 管理者グループまたは SCOM Authors グループのいずれかのメンバーである必要があります。 SCOM 管理サーバー上のローカル管理者は、すべての権限と、SCOM 管理者グループに与えられているアクセス許可があります。  
  
-   管理する各 BizTalk サーバーに SCOM エージェントを展開することで、BizTalk サーバーを Operations Manager で管理されたコンピューターとして設定します。 SCOM エージェントの展開には、次のタスクが含まれます。  
  
    -   SCOM エージェントをインストールします。  
  
    -   BizTalk SCOM エージェント アカウントを作成します。  
  
    -   構成、**として実行**アカウント。 次のグループに、実行アカウントを追加します。  
  
        -   BizTalk グループ。  
  
        -   BizTalk 管理者。  
  
        -   SSO 管理者。  
  
        -   SSO 関連管理者。  
  
    -   監視を開始します。  
  
-   Operation Manager コンソールで管理されたコンピューターは正常な状態です。  
  
-   必要なユーザーとして実行アカウントやプロファイルなど、設定する必要があるすべてのユーザー アカウントを構成します。 この管理パックには、エージェントごとに特定の資格情報を定義するには、「BizTalk Server 監視アカウント」および「BizTalk Server 検出アカウント」という名前のユーザーとして実行プロファイルが含まれています。 管理パックをインポートした後に、一部のエージェントに対してこの実行プロファイルを使用する必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [この管理パックのファイル](../technical-guides/files-in-this-management-pack.md)  
  
-   [推奨される追加の管理パック](../technical-guides/recommended-additional-management-packs.md)