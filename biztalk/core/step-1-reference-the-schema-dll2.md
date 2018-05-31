---
title: '手順 1: 参照スキーマ DLL2 |Microsoft ドキュメント'
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
ms.openlocfilehash: a5b009e2c79c0ea68030561c51e3a90ceef24eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277530"
---
# <a name="step-1-reference-the-schema-dll"></a><span data-ttu-id="f9ef7-102">手順 1: スキーマ DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-102">Step 1: Reference the Schema DLL</span></span>
<span data-ttu-id="f9ef7-103">BizTalk では、メッセージを変更できません。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-103">In BizTalk, messages are immutable.</span></span> <span data-ttu-id="f9ef7-104">したがって、プロパティ値を変更するには、新しいメッセージを作成して変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-104">Therefore, to change a property value you must create and modify a new message.</span></span> <span data-ttu-id="f9ef7-105">作成して、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-105">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span>  
  
 <span data-ttu-id="f9ef7-106">最初に、ただし、する必要があります、スキーマ DLL を参照、j. d. へのアクセス</span><span class="sxs-lookup"><span data-stu-id="f9ef7-106">First, however, you must reference the schema DLL to gain access to the J.D.</span></span> <span data-ttu-id="f9ef7-107">Edwards コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-107">Edwards context properties.</span></span>  
  
### <a name="to-reference-the-schema-dll"></a><span data-ttu-id="f9ef7-108">スキーマ DLL を参照するには</span><span class="sxs-lookup"><span data-stu-id="f9ef7-108">To reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="f9ef7-109">プロジェクト用の作業フォルダ (たとえば c:\class\JDE\BeginDoc) と、テスト XML を格納するフォルダ (たとえば c:\class\JDE\input) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-109">Create a working folder, for example, c:\class\JDE\BeginDoc, for your project and a folder in which you will put the test XML, for example, c:\class\JDE\input.</span></span>  
  
2.  <span data-ttu-id="f9ef7-110">J. d. に要求を送信する静的な送信請求-応答送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-110">Create a Static Solicit-Response Send Port to send the request to J.D.</span></span> <span data-ttu-id="f9ef7-111">Edwards OneWorld です。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-111">Edwards OneWorld.</span></span>  
  
     ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3.  <span data-ttu-id="f9ef7-112">ソリューション エディターで、プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-112">In the Solution Editor, right-click your project.</span></span>  
  
    1.  <span data-ttu-id="f9ef7-113">選択**追加****生成した項目の追加**、順にクリック**アダプターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-113">Select **Add**, select **Add Generated Items**, and then click **Add Adapter**.</span></span>  
  
    2.  <span data-ttu-id="f9ef7-114">Microsoft BizTalk Adapter の j. d. を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-114">Select the Microsoft BizTalk Adapter for J.D.</span></span> <span data-ttu-id="f9ef7-115">Edwards OneWorld および作成したポートです。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-115">Edwards OneWorld and the port you just created.</span></span>  
  
    3.  <span data-ttu-id="f9ef7-116">**アダプターの追加ウィザード** **csales \b4200310**です。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-116">In the **Add Adapter Wizard**, select **CSALES\B4200310**.</span></span>  
  
    4.  <span data-ttu-id="f9ef7-117">をクリックして**完了**メッセージの形式を含むスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-117">Click **Finish** to generate the schema containing the format for the Message.</span></span>  
  
     ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4.  <span data-ttu-id="f9ef7-118">Visual Studio で、ソリューション エクスプローラを開きます。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-118">In Visual Studio, open the Solution Explorer.</span></span>  
  
5.  <span data-ttu-id="f9ef7-119">右クリック**参照**、し、**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-119">Right-click **References**, and then select **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="f9ef7-120">**参照の追加**画面で、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-120">On the **Add Reference** screen, click the **Browse** button.</span></span>  
  
     ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7.  <span data-ttu-id="f9ef7-121">**コンポーネントの選択**画面で、%SystemDrive%\Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin 移動します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-121">On the **Select Component** screen, navigate to %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
8.  <span data-ttu-id="f9ef7-122">選択**Microsoft.Adapters.JDEProperties.dll**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-122">Select **Microsoft.Adapters.JDEProperties.dll**, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="f9ef7-123">**参照の追加**に 画面で、DLL が表示されます、**選択されたコンポーネント**セクションです。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-123">On the **Add Reference** screen, the DLL appears in the **Selected Components** section.</span></span>  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. <span data-ttu-id="f9ef7-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-124">Click **OK**.</span></span>  
  
11. <span data-ttu-id="f9ef7-125">オーケストレーションをダブルクリックしてオーケストレーション デザイナにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-125">Double-click your orchestration to access the Orchestration Designer.</span></span>  
  
     <span data-ttu-id="f9ef7-126">\- または -</span><span class="sxs-lookup"><span data-stu-id="f9ef7-126">\- OR -</span></span>  
  
     <span data-ttu-id="f9ef7-127">選択**ビュー****その他のウィンドウ**、順にクリック**オーケストレーションの種類**。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-127">Select **View**, select **Other Windows**, and then click **Orchestration View**.</span></span>  
  
     <span data-ttu-id="f9ef7-128">[オーケストレーションの種類] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-128">The Orchestration View appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ef7-129">参照</span><span class="sxs-lookup"><span data-stu-id="f9ef7-129">See Also</span></span>  
 <span data-ttu-id="f9ef7-130">[手順 2: オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md) </span><span class="sxs-lookup"><span data-stu-id="f9ef7-130">[Step 2: Create the Orchestration](../core/step-2-create-the-orchestration1.md) </span></span>  
 <span data-ttu-id="f9ef7-131">[手順 3: が完了し、プロジェクトを実行](../core/step-3-complete-and-run-the-project2.md) </span><span class="sxs-lookup"><span data-stu-id="f9ef7-131">[Step 3: Complete and Run the Project](../core/step-3-complete-and-run-the-project2.md) </span></span>  
 [<span data-ttu-id="f9ef7-132">手順 4: サンプル XML BeginDoc を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ef7-132">Step 4: Create a Sample XML BeginDoc</span></span>](../core/step-4-create-a-sample-xml-begindoc1.md)