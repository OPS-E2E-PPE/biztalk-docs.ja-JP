---
title: インスタンス メッセージを生成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: a911e4b0f1167e8ec200dad65b8dacb94bb08be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254402"
---
# <a name="how-to-generate-instance-messages"></a><span data-ttu-id="fa05f-102">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="fa05f-102">How to Generate Instance Messages</span></span>
<span data-ttu-id="fa05f-103">完成したスキーマをチェックする方法の 1 つとして、そのスキーマからサンプルのインスタンス メッセージを生成する方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa05f-103">After you have constructed a schema, one way to check your work is to generate a sample instance message from the schema.</span></span> <span data-ttu-id="fa05f-104">スキーマ ツリーまたはスキーマの XSD (XML Schema Definition) 言語表記をチェックするよりも、インスタンス メッセージでチェックした方があらゆる点で簡単です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-104">In many ways, looking at an instance message is much more straightforward than looking at either the schema tree or the XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="fa05f-105">これは、スキーマでは、対応するインスタンス メッセージについて、すべてのバリエーションが定義されている必要があるが、インスタンス メッセージでは、スキーマによって指定された形式でデータを伝達すれば十分であるためです。</span><span class="sxs-lookup"><span data-stu-id="fa05f-105">This is because the schema needs to describe all of the possible variations of the corresponding instance messages, and a specific instance message just needs to convey some data by using the format specified by the schema.</span></span> <span data-ttu-id="fa05f-106">生成されたインスタンス メッセージはあくまでサンプルであり、対応するスキーマによって定義された構造がすべて反映されているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fa05f-106">The generated instance message is a sample and may not show all of the structures defined by the corresponding schema.</span></span>  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a><span data-ttu-id="fa05f-107">生成後のインスタンス メッセージが格納されるファイルを明示的に指定するには</span><span class="sxs-lookup"><span data-stu-id="fa05f-107">To explicitly specify a file to contain the generated instance message</span></span>  
  
1.  <span data-ttu-id="fa05f-108">ソリューション エクスプ ローラーで、インスタンス メッセージを生成し、をクリックするスキーマを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-108">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa05f-109">必要に応じて、プロパティ ウィンドウで、展開、**全般**のセクション、**全般**の正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="fa05f-109">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="fa05f-110">**出力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) に生成されたインスタンス メッセージが配置される、クリックしてファイルを参照する、値フィールドの右端にあるボタン**保存**です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-110">In the **Output Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file into which generated instance messages will be placed, and then click **Save**.</span></span>  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a><span data-ttu-id="fa05f-111">生成するインスタンス メッセージの種類を指定するには</span><span class="sxs-lookup"><span data-stu-id="fa05f-111">To specify the type of the generated instance message</span></span>  
  
1.  <span data-ttu-id="fa05f-112">ソリューション エクスプ ローラーで、インスタンス メッセージを生成し、をクリックするスキーマを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-112">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa05f-113">必要に応じて、プロパティ ウィンドウで、展開、**全般**のセクション、**全般**の正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="fa05f-113">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="fa05f-114">**インスタンスの出力の種類の生成**プロパティの値フィールド、いずれかを選択するドロップダウン リストを使用して一覧**XML**または**ネイティブ**を生成するインスタンス メッセージの種類として。</span><span class="sxs-lookup"><span data-stu-id="fa05f-114">In the **Generate Instance Output Type** property value field, use the drop-down list to select either **XML** or **Native** as the type of the instance message to be generated.</span></span>  
  
     <span data-ttu-id="fa05f-115">**XML**既定値です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-115">**XML** is the default value.</span></span>  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a><span data-ttu-id="fa05f-116">スキーマに対応するサンプルのインスタンス メッセージを生成するには</span><span class="sxs-lookup"><span data-stu-id="fa05f-116">To generate a sample instance message for a schema</span></span>  
  
1.  <span data-ttu-id="fa05f-117">ソリューション エクスプ ローラーで、インスタンス メッセージを生成し、をクリックするスキーマを右クリックして**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-117">In Solution Explorer, right-click the schema for which you want to generate an instance message, and then click **Generate Instance**.</span></span>  
  
2.  <span data-ttu-id="fa05f-118">出力ウィンドウに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa05f-118">In the Output window, view the results.</span></span> <span data-ttu-id="fa05f-119">このウィンドウには、成功とエラーのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa05f-119">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa05f-120">出力ウィンドウまたはタスク一覧ウィンドウが開いておらず、インスタンス メッセージの生成に成功したか失敗したかの情報が表示されない場合は、これらのウィンドウを手動で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fa05f-120">If the Output window and/or the Task List window did not open and display information about whether the instance generation succeeded or failed, you can open them manually.</span></span> <span data-ttu-id="fa05f-121">これらのウィンドウの管理に関する詳細については、次を参照してください。[を管理するその他の Visual Studio の Windows](../core/how-to-manage-other-visual-studio-windows.md)です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-121">For more information about managing these windows, see [Managing Other Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa05f-122">値を指定しない場合、**ルート参照**プロパティ、BizTalk エディターは、スキーマの最初のルート ノードのサンプル インスタンス メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="fa05f-122">If you do not specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for the first root node in the schema.</span></span> <span data-ttu-id="fa05f-123">値を指定する場合、**ルート参照**プロパティ、BizTalk エディターには、そのルートのサンプル インスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fa05f-123">If you specify a value for the **Root Reference** property, BizTalk Editor generates a sample instance message for that root.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa05f-124">特定のスキーマから生成されたインスタンス メッセージが、同じスキーマを使った検証に合格しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa05f-124">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="fa05f-125">このような場合の詳細については、次を参照してください。[に関する既知の問題のスキーマの生成と検証](../core/known-issues-with-schema-generation-and-validation.md)です。</span><span class="sxs-lookup"><span data-stu-id="fa05f-125">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="fa05f-126">一般に、する生成インスタンス メッセージを編集しを表すようにより現実的なシナリオが含まれているデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="fa05f-126">Generally, you want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="fa05f-127">インスタンス メッセージを修正してから、スキーマを検証してください。</span><span class="sxs-lookup"><span data-stu-id="fa05f-127">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa05f-128">参照</span><span class="sxs-lookup"><span data-stu-id="fa05f-128">See Also</span></span>  
 <span data-ttu-id="fa05f-129">[スキーマのテスト](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="fa05f-129">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="fa05f-130">[スキーマの検証](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="fa05f-130">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="fa05f-131">インスタンス メッセージの生成と検証</span><span class="sxs-lookup"><span data-stu-id="fa05f-131">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)