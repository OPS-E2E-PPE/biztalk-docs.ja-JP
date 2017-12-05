---
title: "アラートの頻度を変更する方法を評価 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f921699e9a98724c8ca2c36f99d7eb9b9848875
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a><span data-ttu-id="7df32-102">警告を評価する頻度を変更する方法</span><span class="sxs-lookup"><span data-stu-id="7df32-102">How to Change the Frequency With Which Alerts Are Evaluated</span></span>
<span data-ttu-id="7df32-103">SQL Notification Services ジェネレーターを既定の設定で展開すると、BAM イベント プロバイダーで発生するイベントに対してタイムリーに対応できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7df32-103">There are cases in which the SQL Notifications services generator may not keep up with events being raised by the BAM event provider when deployed with the default settings.</span></span> <span data-ttu-id="7df32-104">Notification Services の adf.xml ファイルを変更することで、警告のイベントを評価する頻度 (クォンタム期間) を上げることができます。</span><span class="sxs-lookup"><span data-stu-id="7df32-104">You can increase the frequency (the quantum duration) with which events are evaluated for alerts by modifying the Notification Services adf.xml file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7df32-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="7df32-105">Prerequisites</span></span>  
 <span data-ttu-id="7df32-106">ここで示す手順を実行するには、プライマリ インポート データベースの読み取りと書き込みのアクセス許可を持つ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループ、一般には [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7df32-106">To perform this procedure you must be logged on as a member of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that has permissions to read and write the Primary Import database, typically this will be a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a><span data-ttu-id="7df32-107">Notification Services ジェネレーターのクォンタム期間を変更するには</span><span class="sxs-lookup"><span data-stu-id="7df32-107">To modify the Notification Services generator quantum duration</span></span>  
  
1.  <span data-ttu-id="7df32-108">Notification Services コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7df32-108">Open the Notification Services Command prompt.</span></span> <span data-ttu-id="7df32-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2005**をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="7df32-109">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="7df32-110">Notification Services 構成ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="7df32-110">Get the Notification Services configuration file.</span></span> <span data-ttu-id="7df32-111">コマンド プロンプトで次のように入力します。: **cscript ProcessBamNSFiles.vbs--get config.xml adf.xml \<PimaryImport データベース サーバー\> \< PimaryImport データベース名\>**です。</span><span class="sxs-lookup"><span data-stu-id="7df32-111">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Get config.xml adf.xml \<PimaryImport database server\> \< PimaryImport database name\>**.</span></span>  
  
3.  <span data-ttu-id="7df32-112">変更または追加、 \<QuantumDuration\>要素の下、 \<ApplicationExecutionSettings\>内のノード、adf.xml ファイル。</span><span class="sxs-lookup"><span data-stu-id="7df32-112">Modify or add the \<QuantumDuration\> element under the \<ApplicationExecutionSettings\> node in the in the adf.xml file.</span></span> <span data-ttu-id="7df32-113">QuantumDuration 要素の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803)です。</span><span class="sxs-lookup"><span data-stu-id="7df32-113">For more information on the QuantumDuration element, see [http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803).</span></span>  
  
4.  <span data-ttu-id="7df32-114">コマンド プロンプトで次のように入力します。: **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport データベース サーバー\> \< PimaryImport データベース名\>です。**</span><span class="sxs-lookup"><span data-stu-id="7df32-114">At the command prompt, type: **cscript ProcessBamNSFiles.vbs -Update  config.xml adf.xml  \<PimaryImport database server\> \< PimaryImport database name\>.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df32-115">参照</span><span class="sxs-lookup"><span data-stu-id="7df32-115">See Also</span></span>  
 [<span data-ttu-id="7df32-116">Notification Services 構成ファイル用の BAM コマンド ライン スクリプト</span><span class="sxs-lookup"><span data-stu-id="7df32-116">BAM Command-Line Script for Notification Services Configuration Files</span></span>](../core/bam-command-line-script-for-notification-services-configuration-files.md)