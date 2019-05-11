---
title: 手順 1:スキーマ DLL2 の参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82802f13ca772f0604c78efd22c4c3978f387516
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392813"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="8163b-102">手順 1:スキーマ DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="8163b-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="8163b-103">BizTalk メッセージは変更できません。</span><span class="sxs-lookup"><span data-stu-id="8163b-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="8163b-104">そのため、プロパティ値を変更するには、作成し、新しいメッセージを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8163b-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="8163b-105">作成し、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="8163b-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="8163b-106">最初に、ただし、する必要があります、スキーマ DLL を参照、j. d. へのアクセス</span><span class="sxs-lookup"><span data-stu-id="8163b-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="8163b-107">Edwards コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8163b-107">Edwards context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="8163b-108">スキーマ DLL を参照するには</span><span class="sxs-lookup"><span data-stu-id="8163b-108">To reference the schema DLL</span></span>  
  
1. <span data-ttu-id="8163b-109">たとえば、c:\class\JDE\BeginDoc プロジェクトとテストは、XML c:\class\JDE\input などを格納するフォルダーを作業フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8163b-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2. <span data-ttu-id="8163b-110">J. d. に要求を送信するには、静的な送信請求-応答送信ポートの作成します。</span><span class="sxs-lookup"><span data-stu-id="8163b-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="8163b-111">Edwards OneWorld します。</span><span class="sxs-lookup"><span data-stu-id="8163b-111">Edwards OneWorld.</span></span>  
  
    <span data-ttu-id="8163b-112">![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")</span><span class="sxs-lookup"><span data-stu-id="8163b-112">![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")</span></span>  
  
3. <span data-ttu-id="8163b-113">ソリューション エディターでは、プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="8163b-113">In the Solution Editor, right-click your project.</span></span>  
  
   1. <span data-ttu-id="8163b-114">選択**追加**を選択します**生成した項目の追加**、 をクリックし、**アダプターの追加**します。</span><span class="sxs-lookup"><span data-stu-id="8163b-114">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
   2. <span data-ttu-id="8163b-115">J. d. の Microsoft BizTalk アダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="8163b-115">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="8163b-116">Edwards OneWorld および作成したポート。</span><span class="sxs-lookup"><span data-stu-id="8163b-116">Edwards OneWorld and the port you just created.</span></span>  
  
   3. <span data-ttu-id="8163b-117">**アダプターの追加ウィザード**、 **CSALES\B4200310**します。</span><span class="sxs-lookup"><span data-stu-id="8163b-117">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
   4. <span data-ttu-id="8163b-118">をクリックして**完了**メッセージの形式を含むスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="8163b-118">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
      <span data-ttu-id="8163b-119">![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")</span><span class="sxs-lookup"><span data-stu-id="8163b-119">![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")</span></span>  
  
4. <span data-ttu-id="8163b-120">Visual Studio で、ソリューション エクスプ ローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="8163b-120">In Visual Studio, open the Solution Explorer.</span></span>  
  
5. <span data-ttu-id="8163b-121">右クリックして**参照**、し、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8163b-121">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6. <span data-ttu-id="8163b-122">**参照の追加**画面で、、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8163b-122">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
    <span data-ttu-id="8163b-123">![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")</span><span class="sxs-lookup"><span data-stu-id="8163b-123">![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")</span></span>  
  
7. <span data-ttu-id="8163b-124">**コンポーネントの選択**画面には、%SystemDrive%\Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin に移動します。</span><span class="sxs-lookup"><span data-stu-id="8163b-124">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8. <span data-ttu-id="8163b-125">選択**Microsoft.Adapters.JDEProperties.dll**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8163b-125">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="8163b-126">**参照の追加**に画面で、DLL が表示されます、**選択されたコンポーネント**セクション。</span><span class="sxs-lookup"><span data-stu-id="8163b-126">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     <span data-ttu-id="8163b-127">![](../core/media/jde-properties-selection.gif "JDE_properties_selection")</span><span class="sxs-lookup"><span data-stu-id="8163b-127">![](../core/media/jde-properties-selection.gif "JDE_properties_selection")</span></span>  
  
10. <span data-ttu-id="8163b-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8163b-128">Click **OK**.</span></span>  
  
11. <span data-ttu-id="8163b-129">オーケストレーション デザイナーにアクセスするオーケストレーションをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8163b-129">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="8163b-130">\- または -</span><span class="sxs-lookup"><span data-stu-id="8163b-130">\- OR -</span></span>  
  
     <span data-ttu-id="8163b-131">選択**ビュー**を選択します**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="8163b-131">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="8163b-132">オーケストレーション ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8163b-132">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8163b-133">参照</span><span class="sxs-lookup"><span data-stu-id="8163b-133">See Also</span></span>  
 <span data-ttu-id="8163b-134">[手順 2:オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="8163b-134">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 <span data-ttu-id="8163b-135">[ステップ 3:完了して、プロジェクトを実行](../core/step-3-complete-and-run-the-project2.md) </span><span class="sxs-lookup"><span data-stu-id="8163b-135">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project2.md) </span></span>  
 [<span data-ttu-id="8163b-136">手順 4:サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="8163b-136">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)