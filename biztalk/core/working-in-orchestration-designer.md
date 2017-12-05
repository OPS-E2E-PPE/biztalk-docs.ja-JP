---
title: "オーケストレーション デザイナーでの作業 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, saving
- deleting, orchestrations
- projects, orchestrations
- orchestrations, properties
- orchestrations, creating
- creating, orchestrations
- naming conventions, orchestrations
- orchestrations, naming conventions
- orchestrations, deleting
ms.assetid: 13e72b41-d9b6-4508-9a44-b3c7c1804f36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52eb574f9f6b55b784357ff03c05ccb23774fecb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="working-in-orchestration-designer"></a><span data-ttu-id="5c8d8-102">オーケストレーション デザイナーの操作</span><span class="sxs-lookup"><span data-stu-id="5c8d8-102">Working in Orchestration Designer</span></span>
<span data-ttu-id="5c8d8-103">BizTalk プロジェクトを起動すると、新しいオーケストレーションを作成したり、既存のオーケストレーションをプロジェクトに追加したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-103">After you have started a BizTalk project, you can create new orchestrations and add existing orchestrations to the project.</span></span> <span data-ttu-id="5c8d8-104">オーケストレーションの作成と保存、プロジェクトへの既存のオーケストレーションの追加や削除、オーケストレーションの名前の変更、およびオーケストレーションのプロパティの設定については、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-104">See the following procedures to create and save an orchestration, to add an existing orchestration to a project or remove one from it, to change the name of an orchestration, and to set orchestration properties.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="5c8d8-105">オーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-105">To create an orchestration</span></span>  
  
1.  <span data-ttu-id="5c8d8-106">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、選択**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-106">In Solution Explorer, right-click the project name, select **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="5c8d8-107">**新しい項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**BizTalk プロジェクトの項目**、し、、**テンプレート** ウィンドウで、をクリックして**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-107">In the **Add New Item** dialog box, in the **Categories** pane, click **BizTalk Project Items**, and then in the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
3.  <span data-ttu-id="5c8d8-108">**名前** ダイアログ ボックスの下部にあるボックスで、オーケストレーションの名前を指定し、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-108">In the **Name** box at the bottom of the dialog box, supply a name for the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5c8d8-109">新しいオーケストレーションが作成されてオーケストレーション デザイナーに表示され、対応する .odx ファイルが作成されてソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-109">The new orchestration is created and displayed in Orchestration Designer, and a corresponding .odx file is created and displayed in Solution Explorer.</span></span>  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a><span data-ttu-id="5c8d8-110">既存のオーケストレーションをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-110">To add an existing orchestration to a project</span></span>  
  
1.  <span data-ttu-id="5c8d8-111">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-111">In Solution Explorer, right-click the project name, click **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="5c8d8-112">**既存項目の追加**ダイアログ ボックスで、オーケストレーションを含むディレクトリに移動し、オーケストレーションを選択してをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-112">In the **Add Existing Item** dialog box, navigate to the directory containing the orchestration, select the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5c8d8-113">オーケストレーションがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-113">The orchestration is added to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c8d8-114">既存のファイルを追加すると、そのファイルはプロジェクトにコピーされます </span><span class="sxs-lookup"><span data-stu-id="5c8d8-114">When you add an existing file, the file is copied to your project.</span></span> <span data-ttu-id="5c8d8-115">(ファイルは単純に参照によって追加されるわけではありません)。プロジェクト内でファイルを変更した場合、元のファイルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-115">(The file is not simply added by reference.) If you change the file in your project, the original file is left unchanged.</span></span>  
  
### <a name="to-change-the-name-of-an-orchestration"></a><span data-ttu-id="5c8d8-116">オーケストレーションの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-116">To change the name of an orchestration</span></span>  
  
1.  <span data-ttu-id="5c8d8-117">ソリューション エクスプ ローラーで、変更、およびをクリックする .odx ファイルを右クリックし**の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-117">In Solution Explorer, right-click the .odx file you want to change, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="5c8d8-118">新しいファイル名を入力して、<localizedText>Enter</localizedText> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-118">Type the new file name you want, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c8d8-119">オーケストレーションの種類の名前を変更するには、プロパティ ウィンドウを表示し、デザイン画面でクリックし、値の変更をする可能性がありますも .odx ファイルの名前を変更すると、 **Typename**のプロパティ、オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-119">When you change the name of an .odx file, you might also want to change the name of the orchestration type by clicking on the design surface to bring up the Properties window and changing the value of the **Typename** property of the orchestration.</span></span>  
  
### <a name="to-save-an-orchestration"></a><span data-ttu-id="5c8d8-120">オーケストレーションを保存するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-120">To save an orchestration</span></span>  
  
-   <span data-ttu-id="5c8d8-121">**ファイル** メニューのをクリックして**保存\<オーケストレーション名\>**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-121">On the **File** menu, click **Save \<orchestration name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c8d8-122">オーケストレーション ファイルは、utf-8 として保存されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-122">Orchestration files are saved as UTF-8.</span></span>  <span data-ttu-id="5c8d8-123">スキーマ、マップ、およびパイプラインは、utf-16 として保存されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-123">Schemas, maps, and pipelines are saved as UTF-16.</span></span>  
  
### <a name="to-remove-an-orchestration-from-a-project"></a><span data-ttu-id="5c8d8-124">オーケストレーションをプロジェクトから削除するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-124">To remove an orchestration from a project</span></span>  
  
-   <span data-ttu-id="5c8d8-125">ソリューション エクスプ ローラーで、削除、およびをクリックするファイルを右クリックして**プロジェクトから除外**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-125">In Solution Explorer, right-click the file you want to remove, and then click **Exclude From Project**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c8d8-126">プロジェクトからオーケストレーションを削除し、ファイルを完全に削除をクリックして**削除**代わりにします。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-126">To remove the orchestration from a project and permanently delete the file, click **Delete** instead.</span></span>  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a><span data-ttu-id="5c8d8-127">除外されたオーケストレーションをプロジェクトに含めるには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-127">To include an excluded orchestration in a project</span></span>  
  
-   <span data-ttu-id="5c8d8-128">ソリューション エクスプ ローラーで、をクリックして、**すべて表示**ツール バー ボタン、.odx ファイルを右クリックして選択**プロジェクトに含める**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-128">In Solution Explorer, click the **Show All** toolbar button, right-click the .odx file you want, and select **Include in Project**.</span></span>  
  
### <a name="to-set-orchestration-properties"></a><span data-ttu-id="5c8d8-129">オーケストレーションのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="5c8d8-129">To set orchestration properties</span></span>  
  
1.  <span data-ttu-id="5c8d8-130">プロジェクト内の .odx ファイルをダブルクリックするか、処理領域内でオーケストレーションが含まれているタブをクリックして、オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-130">Open the orchestration by double-clicking on the .odx file in the project, or by selecting the tab containing the orchestration in the Process Area.</span></span>  
  
2.  <span data-ttu-id="5c8d8-131">オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-131">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
     <span data-ttu-id="5c8d8-132">- または -</span><span class="sxs-lookup"><span data-stu-id="5c8d8-132">—Or—</span></span>  
  
     <span data-ttu-id="5c8d8-133">クリックして、**プロセス領域**オーケストレーション デザイン画面の背景。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-133">Click the **Process Area** background of the Orchestration Design Surface.</span></span>  
  
3.  <span data-ttu-id="5c8d8-134">[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-134">In the Properties window, specify the following properties.</span></span> <span data-ttu-id="5c8d8-135">特定の状況下でのみ表示されるプロパティもあります。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-135">Note that some properties appear only under certain circumstances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c8d8-136">オーケストレーションの名前、ポートの種類、およびマルチパート メッセージの種類は、モジュールのスコープ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-136">The names of orchestrations, port types and multi-part message types must be unique within the scope of a module.</span></span>  
  
    |<span data-ttu-id="5c8d8-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c8d8-137">Property</span></span>|<span data-ttu-id="5c8d8-138">Description</span><span class="sxs-lookup"><span data-stu-id="5c8d8-138">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="5c8d8-139">Batch</span><span class="sxs-lookup"><span data-stu-id="5c8d8-139">Batch</span></span>|<span data-ttu-id="5c8d8-140">アトミックのトランザクションであるオーケストレーションを他のインスタンスと共にバッチ処理できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-140">Determines whether an orchestration that is an atomic transaction can be batched with other instances.</span></span>|  
    |<span data-ttu-id="5c8d8-141">[補正]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-141">Compensation</span></span>|<span data-ttu-id="5c8d8-142">オーケストレーションで実行する補正の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-142">Specifies what type of compensation to perform on the orchestration.</span></span>|  
    |<span data-ttu-id="5c8d8-143">[分離レベル]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-143">Isolation Level</span></span>|<span data-ttu-id="5c8d8-144">トランザクション オーケストレーションについて、同時実行トランザクション間でアクセスできるデータのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-144">For transactional orchestrations, determines the degree to which data is accessible among concurrent transactions.</span></span>|  
    |<span data-ttu-id="5c8d8-145">[エクスポート可能なモジュール]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-145">Module Exportable</span></span>|<span data-ttu-id="5c8d8-146">BPEL4WS へのエクスポートが可能なモジュールかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-146">Determines whether or not the module can be exported to BPEL4WS.</span></span>|  
    |<span data-ttu-id="5c8d8-147">[モジュール XML ターゲットの名前空間]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-147">Module XML Target Namespace</span></span>|<span data-ttu-id="5c8d8-148">BPEL4WS への型のエクスポート時に使用される XML ターゲットの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-148">The XML target namespace used when exporting types to BPEL4WS.</span></span>|  
    |<span data-ttu-id="5c8d8-149">名前空間</span><span class="sxs-lookup"><span data-stu-id="5c8d8-149">Namespace</span></span>|<span data-ttu-id="5c8d8-150">オーケストレーションおよびオーケストレーションの種類を含んでいるモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-150">Determines the name of the containing module that includes the orchestration and the orchestration types.</span></span>|  
    |<span data-ttu-id="5c8d8-151">[エクスポート可能なオーケストレーション]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-151">Orchestration Exportable</span></span>|<span data-ttu-id="5c8d8-152">このオーケストレーションが BPEL4WS にエクスポート可能かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-152">Indicates whether this orchestration is intended to be exportable to BPEL4WS.</span></span>|  
    |<span data-ttu-id="5c8d8-153">[オーケストレーションの XML ターゲットの名前空間]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-153">Orchestration XML Target Namespace</span></span>|<span data-ttu-id="5c8d8-154">このオーケストレーションを BPEL4WS にエクスポートするときに使用される XML ターゲットの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-154">The XML target namespace used when exporting this orchestration to BPEL4WS.</span></span>|  
    |<span data-ttu-id="5c8d8-155">[再試行]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-155">Retry</span></span>|<span data-ttu-id="5c8d8-156">トランザクション オーケストレーションが失敗した場合に再試行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-156">Specify whether to retry a transactional orchestration if it fails.</span></span>|  
    |<span data-ttu-id="5c8d8-157">Timeout</span><span class="sxs-lookup"><span data-stu-id="5c8d8-157">Timeout</span></span>|<span data-ttu-id="5c8d8-158">トランザクション オーケストレーションが非アクティブな場合にエラーを発生させるまでの時間 (秒) です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-158">The time in seconds until a transactional orchestration fails due to inactivity.</span></span>|  
    |<span data-ttu-id="5c8d8-159">[トランザクション識別子]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-159">Transaction Identifier</span></span>|<span data-ttu-id="5c8d8-160">トランザクション オーケストレーションの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-160">Unique identifier for a transactional orchestration.</span></span>|  
    |<span data-ttu-id="5c8d8-161">トランザクションの種類</span><span class="sxs-lookup"><span data-stu-id="5c8d8-161">Transaction Type</span></span>|<span data-ttu-id="5c8d8-162">オーケストレーションがアトミックのトランザクションであるか、長時間トランザクションであるか、またはトランザクションではないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-162">Determines whether the orchestration is an atomic transaction, a long-running transaction, or is not transacted.</span></span>|  
    |<span data-ttu-id="5c8d8-163">型修飾子</span><span class="sxs-lookup"><span data-stu-id="5c8d8-163">Type Modifier</span></span>|<span data-ttu-id="5c8d8-164">オーケストレーション レベルの変数のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-164">Determines the scope of orchestration-level variables:</span></span><br /><br /> <span data-ttu-id="5c8d8-165">プライベート: このオーケストレーションへのアクセスが含まれているモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-165">Private—Access to this orchestration is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="5c8d8-166">パブリック: このオーケストレーションへのアクセスが制限されていません。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-166">Public—Access to this orchestration is not limited.</span></span><br /><br /> <span data-ttu-id="5c8d8-167">内部-このオーケストレーションへのアクセスは、同じプロジェクト内のモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-167">Internal—Access to this orchestration is limited to modules within the same project.</span></span>|  
    |<span data-ttu-id="5c8d8-168">[型名]</span><span class="sxs-lookup"><span data-stu-id="5c8d8-168">Typename</span></span>|<span data-ttu-id="5c8d8-169">含んでいるモジュールにおけるこのオーケストレーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-169">Determines the name of this orchestration within the containing module.</span></span> <span data-ttu-id="5c8d8-170">**注:**場合、ルート レベルの名前空間と同じである型名を使用するメッセージを定義して、変数を実行しようと Typename に基づいてそれらに対する割り当て操作時に、オーケストレーション デザイナーのエラーを受信可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-170">**Note:**  If you to use a Typename that is the same as a root-level namespace, you may receive an error from Orchestration Designer when you define messages and variables based on the Typename and attempt to perform assign operations on them.</span></span> <span data-ttu-id="5c8d8-171">たとえば、[型名] を System と指定して、System.String のようなメッセージや変数を定義すると、エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5c8d8-171">For example, if you specify a Typename of System, and then define messages and variables like System.String, you may receive an error.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c8d8-172">参照</span><span class="sxs-lookup"><span data-stu-id="5c8d8-172">See Also</span></span>  
 <span data-ttu-id="5c8d8-173">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="5c8d8-173">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="5c8d8-174">[オーケストレーションに図形を追加する方法](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="5c8d8-174">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 <span data-ttu-id="5c8d8-175">[オーケストレーションにパラメーターを追加する方法](../core/how-to-add-parameters-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="5c8d8-175">[How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="5c8d8-176">選択アイテムの種類 ダイアログ ボックスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5c8d8-176">How to Use the Select Artifact Type Dialog Box</span></span>](../core/how-to-use-the-select-artifact-type-dialog-box.md)