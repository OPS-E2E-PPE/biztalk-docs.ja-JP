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
ms.openlocfilehash: 83f034a41fffa0c646b0173e8b889c20373760ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967155"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>ライブ データまたはアーカイブ済みのデータのデータ ソースを選択する方法
BizTalktracking では、アーカイブ済みのデータとライブ データの両方にアクセスできます。 メインのライブまたはアーカイブ済みのデータ ソースを選択する**BizTalk Server 管理**BizTalk Server 管理コンソールのノード。  既定のソースは、BizTalk 管理サーバーから取得されるライブ データです。 アーカイブ済みのデータを使用する場合は、使用する適切なサーバーとデータベースを選択する必要があります。  

-   アーカイブされたデータ: アーカイブされたデータを分析することができます、ビジネスと、システムの両方の傾向を調べます必要なだけさかのぼりためすることができます。 アーカイブ済みのデータを選択する場合、そのデータが格納された SQL Server および SQL データベースも選択する必要があります。  

     アーカイブ済みのデータが選択して指定**既存の追跡データベースに接続しています.**.  

-   ライブ データ: ライブ データを分析を識別し、開発環境またはステージング環境の問題を解決できるように、オーケストレーションとパイプラインを監視できます。 メッセージが保留されている原因など、システムの問題もライブ データを監視することで解決できます。  

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

### <a name="to-select-archived-data"></a>アーカイブ済みのデータを選択するには  

1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. [メイン] をクリックして**BizTalk Server 管理**ノード。  

3. クリックして**既存の追跡データベースに接続しています.**  

4. **SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。  

5. **データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。  

6. **[OK]** をクリックします。
