---
title: 既存のメッセージの BRE ポリシーの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe4f95526883f0bc8e79ff0b0c0241aa198747f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377964"
---
# <a name="deploying-bre-policies-for-existing-messages"></a><span data-ttu-id="06fcd-102">既存のメッセージの BRE ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="06fcd-102">Deploying BRE Policies for Existing Messages</span></span>
<span data-ttu-id="06fcd-103">**関連するビジネス ルールを展開するには。**</span><span class="sxs-lookup"><span data-stu-id="06fcd-103">**To deploy the related business rules:**</span></span>  
  
1.  <span data-ttu-id="06fcd-104">クリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-104">Click **Start**, click **Programs**, click **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="06fcd-105">BRE 配置ユーティリティでクリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-105">In BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="06fcd-106">.NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFT MX スキーマ**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-106">In the .NET Global Assembly Cache dialog box, select **SWIFT MX Schema**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="06fcd-107">クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-107">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="06fcd-108">そのアセンブリに展開されているスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-108">Based on the schemas deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="06fcd-109">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。"デプロイが完了しました。</span><span class="sxs-lookup"><span data-stu-id="06fcd-109">When complete, the BRE Deployment Utility displays the following message: "Deployment has completed.</span></span> <span data-ttu-id="06fcd-110">ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"</span><span class="sxs-lookup"><span data-stu-id="06fcd-110">View the log file or Business Rules Composer for details."</span></span>  
  
5.  <span data-ttu-id="06fcd-111">SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="06fcd-111">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="06fcd-112">Windows エクスプ ローラーを参照 *\<ドライブ\>* : \Documents and 別のバックアップ データをフォルダーに表示される BREDeploymentLog.txt をログ ファイルことを確認します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-112">In Windows Explorer, browse to *\<drive\>*:\Documents and Settings\All Users\Application Data to confirm that the log file BREDeploymentLog.txt appears in the folder.</span></span>  
  
7.  <span data-ttu-id="06fcd-113">をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="06fcd-113">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="06fcd-114">サービス (ローカル) ウィンドウで、右クリックして**ルール エンジン更新サービス**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="06fcd-114">In the Services (Local) window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>