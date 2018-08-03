---
title: 既存のメッセージの BRE ポリシーを展開する |Microsoft ドキュメント
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
ms.openlocfilehash: 4cd094feabe1ba23a6a73c89aae3a1042b8f7fc9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965008"
---
# <a name="deploying-bre-policies-for-existing-messages"></a><span data-ttu-id="44730-102">既存のメッセージの BRE ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="44730-102">Deploying BRE Policies for Existing Messages</span></span>
<span data-ttu-id="44730-103">**関連するビジネス ルールを展開するには。**</span><span class="sxs-lookup"><span data-stu-id="44730-103">**To deploy the related business rules:**</span></span>  
  
1.  <span data-ttu-id="44730-104">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk Accelerator 用 SWIFT**、順にクリック**BRE 配置ユーティリティ**です。</span><span class="sxs-lookup"><span data-stu-id="44730-104">Click **Start**, click **Programs**, click **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="44730-105">BRE 配置ユーティリティでクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="44730-105">In BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="44730-106">.NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFT MX スキーマ**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="44730-106">In the .NET Global Assembly Cache dialog box, select **SWIFT MX Schema**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="44730-107">をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="44730-107">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="44730-108">そのアセンブリに展開されているスキーマに基づくと、配置ユーティリティ関連するルールを識別それらを発行して、BRE を使用します。</span><span class="sxs-lookup"><span data-stu-id="44730-108">Based on the schemas deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="44730-109">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ:"配置が完了しました。</span><span class="sxs-lookup"><span data-stu-id="44730-109">When complete, the BRE Deployment Utility displays the following message: "Deployment has completed.</span></span> <span data-ttu-id="44730-110">ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"</span><span class="sxs-lookup"><span data-stu-id="44730-110">View the log file or Business Rules Composer for details."</span></span>  
  
5.  <span data-ttu-id="44730-111">SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="44730-111">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="44730-112">Windows エクスプ ローラーで参照*\<ドライブ\>*: \Documents and settings \all \all データをログ ファイル BREDeploymentLog.txt に表示されるフォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="44730-112">In Windows Explorer, browse to *\<drive\>*:\Documents and Settings\All Users\Application Data to confirm that the log file BREDeploymentLog.txt appears in the folder.</span></span>  
  
7.  <span data-ttu-id="44730-113">をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="44730-113">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="44730-114">サービス (ローカル) ウィンドウで右クリック**ルール エンジン更新サービス**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="44730-114">In the Services (Local) window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>