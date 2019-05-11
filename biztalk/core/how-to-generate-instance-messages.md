---
title: インスタンス メッセージを生成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f851a2888fe0dd9a82b86a47d2ca8faa42c8edf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385040"
---
# <a name="how-to-generate-instance-messages"></a><span data-ttu-id="0aa80-102">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="0aa80-102">How to Generate Instance Messages</span></span>
<span data-ttu-id="0aa80-103">スキーマを作成した後、動作を確認する方法の 1 つでは、スキーマからサンプル インスタンス メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-103">After you have constructed a schema, one way to check your work is to generate a sample instance message from the schema.</span></span> <span data-ttu-id="0aa80-104">多くの点で、インスタンス メッセージを見てはスキーマ ツリーまたはスキーマの XML スキーマ定義 (XSD) 言語表記のいずれかを調べるよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="0aa80-104">In many ways, looking at an instance message is much more straightforward than looking at either the schema tree or the XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="0aa80-105">これに対応するインスタンス メッセージのバリエーションを記述する必要があるスキーマとだけが、スキーマで指定された形式を使用して一部のデータを伝達するために必要な特定のインスタンス メッセージであるためにです。</span><span class="sxs-lookup"><span data-stu-id="0aa80-105">This is because the schema needs to describe all of the possible variations of the corresponding instance messages, and a specific instance message just needs to convey some data by using the format specified by the schema.</span></span> <span data-ttu-id="0aa80-106">生成されたインスタンス メッセージ サンプルであり、対応するスキーマによって定義された構造体のすべてを表示しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0aa80-106">The generated instance message is a sample and may not show all of the structures defined by the corresponding schema.</span></span>  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a><span data-ttu-id="0aa80-107">生成されたインスタンス メッセージを格納するファイルを明示的に指定するには</span><span class="sxs-lookup"><span data-stu-id="0aa80-107">To explicitly specify a file to contain the generated instance message</span></span>  
  
1.  <span data-ttu-id="0aa80-108">ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-108">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0aa80-109">必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="0aa80-109">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="0aa80-110">**出力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) 生成されたインスタンス メッセージに、配置をクリックしてのファイルを参照する値のフィールドの右端にあるボタン**保存**します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-110">In the **Output Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file into which generated instance messages will be placed, and then click **Save**.</span></span>  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a><span data-ttu-id="0aa80-111">生成されたインスタンス メッセージの種類を指定するには</span><span class="sxs-lookup"><span data-stu-id="0aa80-111">To specify the type of the generated instance message</span></span>  
  
1.  <span data-ttu-id="0aa80-112">ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-112">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0aa80-113">必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="0aa80-113">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="0aa80-114">**インスタンスの出力の種類の生成**プロパティ値フィールドで、いずれかを選択リストをドロップダウン リストを使って**XML**または**ネイティブ**を生成するインスタンス メッセージの種類として。</span><span class="sxs-lookup"><span data-stu-id="0aa80-114">In the **Generate Instance Output Type** property value field, use the drop-down list to select either **XML** or **Native** as the type of the instance message to be generated.</span></span>  
  
     <span data-ttu-id="0aa80-115">**XML**は既定値です。</span><span class="sxs-lookup"><span data-stu-id="0aa80-115">**XML** is the default value.</span></span>  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a><span data-ttu-id="0aa80-116">スキーマのサンプル インスタンス メッセージを生成するには</span><span class="sxs-lookup"><span data-stu-id="0aa80-116">To generate a sample instance message for a schema</span></span>  
  
1.  <span data-ttu-id="0aa80-117">ソリューション エクスプ ローラーで右クリックして、インスタンス メッセージを生成するスキーマ**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-117">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Generate Instance**.</span></span>  
  
2.  <span data-ttu-id="0aa80-118">[出力] ウィンドウで、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-118">In the Output window, view the results.</span></span> <span data-ttu-id="0aa80-119">このウィンドウには、成功とエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0aa80-119">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0aa80-120">出力ウィンドウおよびタスク一覧 ウィンドウがないを開きに関する情報を表示場合は、インスタンスの生成が成功したかが失敗したことがそれらを手動で開くかどうか。</span><span class="sxs-lookup"><span data-stu-id="0aa80-120">If the Output window and/or the Task List window did not open and display information about whether the instance generation succeeded or failed, you can open them manually.</span></span> <span data-ttu-id="0aa80-121">これらのウィンドウの管理に関する詳細については、次を参照してください。[その他の Visual Studio Windows の管理](../core/how-to-manage-other-visual-studio-windows.md)します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-121">For more information about managing these windows, see [Managing Other Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0aa80-122">値を指定しない場合、**ルート参照**プロパティを BizTalk エディターでは、スキーマの最初のルート ノードのサンプル インスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0aa80-122">If you do not specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for the first root node in the schema.</span></span> <span data-ttu-id="0aa80-123">値を指定する場合、**ルート参照**プロパティを BizTalk エディターには、そのルートのサンプル インスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0aa80-123">If you specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for that root.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0aa80-124">一部のケースのインスタンスがある特定のスキーマから生成されるメッセージは、その同じスキーマの検証を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="0aa80-124">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="0aa80-125">詳細については、このような場合は、次を参照してください。[スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-125">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="0aa80-126">一般に、生成されたインスタンス メッセージを編集し、データが含まれているためより現実的なシナリオを表しますを変更します。</span><span class="sxs-lookup"><span data-stu-id="0aa80-126">Generally, you want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="0aa80-127">この変更されたインスタンス メッセージを使用し、スキーマを検証できます。</span><span class="sxs-lookup"><span data-stu-id="0aa80-127">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa80-128">参照</span><span class="sxs-lookup"><span data-stu-id="0aa80-128">See Also</span></span>  
 <span data-ttu-id="0aa80-129">[スキーマのテスト](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="0aa80-129">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="0aa80-130">[スキーマの検証](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="0aa80-130">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="0aa80-131">インスタンス メッセージの生成および検証</span><span class="sxs-lookup"><span data-stu-id="0aa80-131">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)