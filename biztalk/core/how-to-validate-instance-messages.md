---
title: インスタンス メッセージを検証する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: bd0baa898f801c924cffc5a446aa1a22d063a8fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256794"
---
# <a name="how-to-validate-instance-messages"></a><span data-ttu-id="ec473-102">インスタンス メッセージを検証する方法</span><span class="sxs-lookup"><span data-stu-id="ec473-102">How to Validate Instance Messages</span></span>
<span data-ttu-id="ec473-103">作成したスキーマが正しく構築されているかどうかは、そのスキーマに対して適切な表記になっていることが確認されている、既存のインスタンス メッセージを検証することによってチェックできます。</span><span class="sxs-lookup"><span data-stu-id="ec473-103">After you have constructed a schema, you can check your work by validating a pre-existing instance message that you know is a good representation of such instance messages against the schema.</span></span>  
  
 <span data-ttu-id="ec473-104">このトピックでは、この検証作業を行うための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec473-104">This topic provides step-by-step instructions for this validation task.</span></span>  
  
### <a name="to-validate-an-instance-message-against-a-schema"></a><span data-ttu-id="ec473-105">スキーマを使ってインスタンス メッセージを検証するには</span><span class="sxs-lookup"><span data-stu-id="ec473-105">To validate an instance message against a schema</span></span>  
  
1.  <span data-ttu-id="ec473-106">ソリューション エクスプ ローラーで、スキーマを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ec473-106">In Solution Explorer, right-click the schema, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ec473-107">必要に応じて、プロパティ ウィンドウで、展開、**全般**のセクション、**全般**の正符号をクリックしてタブ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="ec473-107">If necessary, in the Properties window, expand the **General** section of the **General** tab by clicking its plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="ec473-108">**入力インスタンス ファイル名**プロパティの値フィールド、ファイルの名前を入力するか、省略記号ボタン (**.**) ボタンをクリックして、スキーマに対して検証するインスタンス メッセージを含むファイルを参照するフィールドの右端にある**開く**です。</span><span class="sxs-lookup"><span data-stu-id="ec473-108">In the **Input Instance Filename** property value field, either type the name of a file or use the ellipsis (**...**) button at the right end of the value field to browse for a file that contains the instance message to be validated against the schema, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="ec473-109">**ソリューション エクスプ ローラー**スキーマ名を右クリックし、クリックして**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="ec473-109">In **Solution Explorer**, right-click the schema name, and then click **Validate Instance**.</span></span>  
  
5.  <span data-ttu-id="ec473-110">出力ウィンドウに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec473-110">In the Output window, view the results.</span></span> <span data-ttu-id="ec473-111">このウィンドウには、成功とエラーのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec473-111">Success and error messages are displayed in this window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec473-112">特定のスキーマから生成されたインスタンス メッセージが、同じスキーマを使った検証に合格しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec473-112">There are some cases instance messages generated from a particular schema may not pass validation with that same schema.</span></span> <span data-ttu-id="ec473-113">このような場合の詳細については、次を参照してください。[に関する既知の問題のスキーマの生成と検証](../core/known-issues-with-schema-generation-and-validation.md)です。</span><span class="sxs-lookup"><span data-stu-id="ec473-113">For more information about such cases, see [Known Issues with Schema Generation and Validation](../core/known-issues-with-schema-generation-and-validation.md).</span></span> <span data-ttu-id="ec473-114">通常、インスタンス メッセージを生成した後は、実際のシナリオに合わせて修正し、データを変更します。</span><span class="sxs-lookup"><span data-stu-id="ec473-114">Generally, you will want to edit a generated instance message and change the data it contains so that it more realistically represents your scenario.</span></span> <span data-ttu-id="ec473-115">インスタンス メッセージを修正してから、スキーマを検証してください。</span><span class="sxs-lookup"><span data-stu-id="ec473-115">Then use this modified instance message to validate your schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec473-116">参照</span><span class="sxs-lookup"><span data-stu-id="ec473-116">See Also</span></span>  
 <span data-ttu-id="ec473-117">[スキーマのテスト](../core/testing-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="ec473-117">[Testing Schemas](../core/testing-schemas.md) </span></span>  
 <span data-ttu-id="ec473-118">[スキーマの検証](../core/schema-validation1.md) </span><span class="sxs-lookup"><span data-stu-id="ec473-118">[Schema Validation](../core/schema-validation1.md) </span></span>  
 [<span data-ttu-id="ec473-119">インスタンス メッセージの生成と検証</span><span class="sxs-lookup"><span data-stu-id="ec473-119">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)