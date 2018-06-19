---
title: XML 構成からエンドポイント動作の構成要素を作成できません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d906a4-ea85-42d8-8e9e-0a3a7774bcd8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc10a737f2c0a2f344a106868c910a2ecb8144bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286834"
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a>XML 構成からエンドポイント動作の構成要素を作成できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|XML 構成からエンドポイント動作の構成要素を作成できません|  
  
## <a name="explanation"></a>説明  
 このエラーは、アダプターにエンドポイント動作の構成が読み込まれなかったことを示します。 この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンドポイント動作を構成するには、次の手順を実行します。  
  
#### <a name="to-configure-the-endpoint-behavior"></a>エンドポイント動作を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。  
  
9. **動作** セクションで、チェック、 **EndpointBehavior**構成します。