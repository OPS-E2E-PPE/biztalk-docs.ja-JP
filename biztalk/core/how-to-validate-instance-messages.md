---
title: インスタンス メッセージを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6302c6-b56b-4572-aa76-0f4c4599672a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb7d83c8ba847a84a38b2701bb5ca2492559d450
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333180"
---
# <a name="how-to-validate-instance-messages"></a><span data-ttu-id="63fe6-102">インスタンス メッセージを検証する方法</span><span class="sxs-lookup"><span data-stu-id="63fe6-102">How to Validate Instance Messages</span></span>
<span data-ttu-id="63fe6-103">スキーマを作成した後は、スキーマの場合は、このようなインスタンス メッセージの適切な表現であることがわかっている既存のインスタンス メッセージを検証することで、作業を確認できます。</span><span class="sxs-lookup"><span data-stu-id="63fe6-103">After you have constructed a schema, you can check your work by validating a pre-existing instance message that you know is a good representation of such instance messages against the schema.</span></span>  
  
 <span data-ttu-id="63fe6-104">このトピックでは、この検証タスクの詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-104">This topic provides step-by-step instructions for this validation task.</span></span>  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a><span data-ttu-id="63fe6-105">インスタンス メッセージをスキーマに対して検証するには</span><span class="sxs-lookup"><span data-stu-id="63fe6-105">To validate an instance message against a schema</span></span>  
  
1.  <span data-ttu-id="63fe6-106">ソリューション エクスプ ローラーで、スキーマを右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-106">In Solution Explorer, right-click the schema, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="63fe6-107">必要に応じて、展開し、[プロパティ] ウィンドウで、**全般**のセクション、**全般**正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="63fe6-107">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="63fe6-108">**入力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) ボタンをクリックして、スキーマに対して検証するインスタンス メッセージを含むファイルを参照する値のフィールドの右端にある**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-108">In the **Input Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file that contains the instance message to be validated against the schema, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="63fe6-109">**ソリューション エクスプ ローラー**スキーマ名を右クリックし、クリックして**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="63fe6-109">In **Solution Explorer**, right-click the schema name, and then click **Validate Instance**.</span></span>  
  
5.  <span data-ttu-id="63fe6-110">[出力] ウィンドウで、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-110">In the Output window, view the results.</span></span> <span data-ttu-id="63fe6-111">このウィンドウには、成功とエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63fe6-111">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63fe6-112">一部のケースのインスタンスがある特定のスキーマから生成されるメッセージは、その同じスキーマの検証を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="63fe6-112">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="63fe6-113">詳細については、このような場合は、次を参照してください。[スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-113">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="63fe6-114">一般に、生成されたインスタンス メッセージを編集し、シナリオをより現実的に表すようにが含まれているデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="63fe6-114">Generally, you will want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="63fe6-115">この変更されたインスタンス メッセージを使用し、スキーマを検証できます。</span><span class="sxs-lookup"><span data-stu-id="63fe6-115">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fe6-116">参照</span><span class="sxs-lookup"><span data-stu-id="63fe6-116">See Also</span></span>  
 <span data-ttu-id="63fe6-117">[スキーマのテスト](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="63fe6-117">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="63fe6-118">[スキーマの検証](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="63fe6-118">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="63fe6-119">インスタンス メッセージの生成および検証</span><span class="sxs-lookup"><span data-stu-id="63fe6-119">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)