---
title: 前処理および後処理のスクリプト アプリケーション展開のカスタマイズを使用した |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- customizing, applications
- applications, customizing
- scripts, applications
- scripts, customizing
ms.assetid: 47627394-d594-491b-9098-38c5d028a378
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dc0afd7ed042f475a9a008125c968f401e6df92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287170"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a><span data-ttu-id="e94ef-102">処理前および処理後のスクリプトを使用したアプリケーション展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e94ef-102">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>
<span data-ttu-id="e94ef-103">このセクションの各トピックでは、アプリケーションのインポート、インストール、またはアンインストール時にアクションを実行する処理前または処理後のスクリプトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e94ef-103">The topics in this section describe how to create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="e94ef-104">処理前のスクリプトは、アプリケーションのインポートまたはインストールの開始前、およびアンインストールの完了後に 1 つのアクションまたはアクションのセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e94ef-104">Pre-processing scripts perform an action or set of actions before application import or installation starts, and after uninstallation completes.</span></span> <span data-ttu-id="e94ef-105">処理後のスクリプトは、アプリケーションのインポートまたはインストールの完了後、あるいはアンインストールの開始前に 1 つのアクションまたはアクションのセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e94ef-105">Post-processing scripts perform an action or set of actions after application import or installation completes, or before uninstallation starts.</span></span>  
  
 <span data-ttu-id="e94ef-106">たとえば、リソース ファイルをインストール中に上書きされる前にバックアップするには、インストールの前に実行する処理前のスクリプトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e94ef-106">You might, for example, want to include a pre-processing script that will run before installation to back up resource files before they are overwritten during installation.</span></span> <span data-ttu-id="e94ef-107">また、アプリケーションのインストール後に証明書ストアに証明書を追加するには、処理後のスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e94ef-107">Or you might want to run a post-processing script to add a certificate to the certificate store after an application is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e94ef-108">BizTalk Server には、処理前のスクリプトと処理後のスクリプトのサンプルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e94ef-108">BizTalk Server includes sample pre- and post-processing scripts.</span></span> <span data-ttu-id="e94ef-109">サンプル スクリプトの使用方法の詳細については、次を参照してください。[テンプレート (アプリケーションの展開サンプル)](../core/template-application-deployment-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e94ef-109">For information about using the sample scripts, see [Template (Application Deployment Sample)](../core/template-application-deployment-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e94ef-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e94ef-110">In This Section</span></span>  
  
-   [<span data-ttu-id="e94ef-111">処理前または処理後のスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94ef-111">Creating a Pre- or Post-processing Script</span></span>](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="e94ef-112">環境変数が展開の状態を指定する方法</span><span class="sxs-lookup"><span data-stu-id="e94ef-112">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [<span data-ttu-id="e94ef-113">配置時にファイルのアイテムの状態</span><span class="sxs-lookup"><span data-stu-id="e94ef-113">Status of File Artifacts During Deployment</span></span>](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [<span data-ttu-id="e94ef-114">前処理および後処理のスクリプト環境変数</span><span class="sxs-lookup"><span data-stu-id="e94ef-114">Pre- and Post-processing Script Environment Variables</span></span>](../core/pre-and-post-processing-script-environment-variables.md)