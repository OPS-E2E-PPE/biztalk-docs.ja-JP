---
title: 前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ |Microsoft Docs
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
ms.openlocfilehash: 23734f43a479e4e526535b61f0e9b957752e03d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396584"
---
# <a name="using-pre--and-post-processing-scripts-to-customize-application-deployment"></a><span data-ttu-id="0e566-102">前処理および後処理のスクリプトを使用したアプリケーション展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0e566-102">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>
<span data-ttu-id="0e566-103">このセクションのトピックでは、事前作成する方法を記述またはアプリケーションがインポートされるときにアクションを実行する処理後のスクリプトは、インストール、またはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0e566-103">The topics in this section describe how to create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="0e566-104">処理前のスクリプトでは、アプリケーションのインポートまたはインストールの開始前に、およびアンインストールの完了後にアクションまたは一連のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e566-104">Pre-processing scripts perform an action or set of actions before application import or installation starts, and after uninstallation completes.</span></span> <span data-ttu-id="0e566-105">処理後のスクリプトでは、アプリケーションのインポートまたはインストールの完了後、またはアンインストールの開始前に、アクションまたはアクションのセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e566-105">Post-processing scripts perform an action or set of actions after application import or installation completes, or before uninstallation starts.</span></span>  
  
 <span data-ttu-id="0e566-106">たとえば、インストール中に上書きされる前に、リソース ファイルをバックアップしてインストールする前に実行される処理前のスクリプトを追加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e566-106">You might, for example, want to include a pre-processing script that will run before installation to back up resource files before they are overwritten during installation.</span></span> <span data-ttu-id="0e566-107">または、アプリケーションをインストールした後、証明書ストアに証明書の追加の処理後のスクリプトを実行したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e566-107">Or you might want to run a post-processing script to add a certificate to the certificate store after an application is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e566-108">BizTalk Server には、サンプルの前処理および後処理のスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e566-108">BizTalk Server includes sample pre- and post-processing scripts.</span></span> <span data-ttu-id="0e566-109">サンプル スクリプトの使用方法の詳細については、次を参照してください。 [Template (アプリケーションの展開サンプル)](../core/template-application-deployment-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e566-109">For information about using the sample scripts, see [Template (Application Deployment Sample)](../core/template-application-deployment-sample.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e566-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0e566-110">In This Section</span></span>  
  
-   [<span data-ttu-id="0e566-111">処理前または処理後のスクリプトの作成</span><span class="sxs-lookup"><span data-stu-id="0e566-111">Creating a Pre- or Post-processing Script</span></span>](../core/creating-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="0e566-112">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="0e566-112">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)  
  
-   [<span data-ttu-id="0e566-113">展開中のファイル アイテムの状態</span><span class="sxs-lookup"><span data-stu-id="0e566-113">Status of File Artifacts During Deployment</span></span>](../core/status-of-file-artifacts-during-deployment.md)  
  
-   [<span data-ttu-id="0e566-114">処理前および処理後のスクリプト環境変数</span><span class="sxs-lookup"><span data-stu-id="0e566-114">Pre- and Post-processing Script Environment Variables</span></span>](../core/pre-and-post-processing-script-environment-variables.md)