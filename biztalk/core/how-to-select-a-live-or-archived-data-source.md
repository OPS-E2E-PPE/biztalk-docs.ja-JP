---
title: ライブまたはアーカイブ済みのデータ ソースを選択する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5917c4488e047a1956fde66a659754c659f23d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383958"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>ライブまたはアーカイブ済みのデータ ソースを選択する方法
Biztalktracking ではアーカイブ済みとライブの両方のデータにアクセスできます。 メインのライブまたはアーカイブ済みのデータ ソースを選択する**BizTalk Server 管理**BizTalk Server 管理コンソールのノード。  既定のソースは、ライブ データを BizTalk 管理データベースから取得します。 アーカイブされたデータを操作する場合は、適切なサーバー/秒と動作するデータベース/秒を選択する必要があります。  

-   アーカイブされたデータ:アーカイブ済みのデータを分析することができます、ビジネスと、システムの両方の傾向を調べる必要なだけさかのぼりためすることができます。 アーカイブ済みのデータを選択すると場合、は、適切な SQL サーバーと、アーカイブされたデータを含む SQL データベースも選択する必要があります。  

     アーカイブ済みのデータが選択して指定**既存の追跡データベースに接続しています.**.  

-   ライブ データ。ライブ データを分析するには、識別し、開発環境またはステージング環境の問題を解決できるようにオーケストレーションとパイプラインを監視することができます。 ライブ データの監視ではメッセージが保留されている理由など、システムでの問題を修正することもできます。  

     ライブ データが選択して指定**既存のグループに接続しています.**.  

## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  

### <a name="to-select-live-data"></a>ライブ データを選択するには  

1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. [メイン] をクリックして**BizTalk Server 管理**ノード。  

3. クリックして**既存のグループに接続しています.**  

4. **SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。  

5. **データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。  

6. **[OK]** をクリックします。  

### <a name="to-select-archived-data"></a>アーカイブされたデータを選択するには  

1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. [メイン] をクリックして**BizTalk Server 管理**ノード。  

3. クリックして**既存の追跡データベースに接続しています.**  

4. **SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。  

5. **データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。  

6. **[OK]** をクリックします。
