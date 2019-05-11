---
title: アセンブリを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68af9966181209b50a4cfb5ee484264d32c60d4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401803"
---
# <a name="how-to-update-an-assembly"></a><span data-ttu-id="b0e96-102">アセンブリを更新する方法</span><span class="sxs-lookup"><span data-stu-id="b0e96-102">How to Update an Assembly</span></span>
<span data-ttu-id="b0e96-103">このトピックでは、アセンブリと Visual Studio 2010 を使用するアセンブリがデプロイされるアプリケーションのバージョンを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-103">This topic describes how to update the version of an assembly and the application that an assembly is deployed to using Visual Studio 2010.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0e96-104">新しいバージョンのアセンブリを更新する場合は、アプリケーションを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0e96-104">If you are updating an assembly with a new version, you do not need to restart the application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0e96-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b0e96-105">Prerequisites</span></span>  
 <span data-ttu-id="b0e96-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0e96-106">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="updating-an-assembly"></a><span data-ttu-id="b0e96-107">アセンブリの更新</span><span class="sxs-lookup"><span data-stu-id="b0e96-107">Updating an Assembly</span></span>  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a><span data-ttu-id="b0e96-108">アセンブリのバージョン番号をインクリメントするには</span><span class="sxs-lookup"><span data-stu-id="b0e96-108">To increment the version number of an assembly</span></span>  
  
1.  <span data-ttu-id="b0e96-109">ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-109">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b0e96-110">**プロジェクト デザイナー**、クリックして、**アプリケーション**タブ。</span><span class="sxs-lookup"><span data-stu-id="b0e96-110">In the **Project Designer**, click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="b0e96-111">右側のウィンドウで次のようにクリックします。**アセンブリ情報**します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-111">In the right pane, click **Assembly Information**.</span></span>  
  
4.  <span data-ttu-id="b0e96-112">**アセンブリ情報** ダイアログ ボックスで、指定の値、**アセンブリ バージョン**アセンブリのバージョン番号を大きくフィールド。</span><span class="sxs-lookup"><span data-stu-id="b0e96-112">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to increase the assembly version number.</span></span> <span data-ttu-id="b0e96-113">メジャーまたはマイナー バージョン番号のみを増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0e96-113">You should increase only the major or minor version number.</span></span> <span data-ttu-id="b0e96-114">メジャー バージョン番号は、シーケンスの最初の桁 (***n***.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0 ***。n***.0.0) です。</span><span class="sxs-lookup"><span data-stu-id="b0e96-114">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span> <span data-ttu-id="b0e96-115">BizTalk Server では、0.0 などのシーケンスの後のバージョン番号の変更は認識されません。***n***.0 や 0.0.0 ***。n***します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-115">BizTalk Server will not recognize a version number change that is later in the sequence, such as 0.0.***n***.0 or 0.0.0.***n***.</span></span>  
  
5.  <span data-ttu-id="b0e96-116">をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b0e96-116">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
6.  <span data-ttu-id="b0e96-117">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-117">Save the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0e96-118">アセンブリのバージョンを増やすときに、スキーマの競合を回避するために、パイプライン デザイナと BizTalk エクスプローラ オブジェクト モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-118">Use the Pipeline Designer and BizTalk Explorer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a><span data-ttu-id="b0e96-119">アセンブリが展開されているアプリケーションを変更するには</span><span class="sxs-lookup"><span data-stu-id="b0e96-119">To change the application that an assembly is deployed to</span></span>  
  
1.  <span data-ttu-id="b0e96-120">ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b0e96-121">**プロジェクト デザイナー**、クリックして、**展開**タブ。</span><span class="sxs-lookup"><span data-stu-id="b0e96-121">In the **Project Designer**, click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="b0e96-122">右側のウィンドウで アプリケーション名を指定します、**アプリケーション名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="b0e96-122">In the right pane, specify the application name in the **Application Name** field.</span></span>  
  
4.  <span data-ttu-id="b0e96-123">いることを確認、**グローバル アセンブリ キャッシュにインストール**プロパティに設定されて**True**します。</span><span class="sxs-lookup"><span data-stu-id="b0e96-123">Ensure that the **Install to Global Assembly Cache** property is set to **True**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0e96-124">ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b0e96-124">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>