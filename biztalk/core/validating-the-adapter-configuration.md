---
title: "アダプター構成の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03054332e0cd2117c1219afec3dd1aa0a09d6bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="4a442-102">アダプターの構成情報の検証</span><span class="sxs-lookup"><span data-stu-id="4a442-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="4a442-103">送信ポートと受信場所を追加中にするように求められますでカスタム プロパティを構成する、  **\<** *アダプター名* **\>トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4a442-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<***Adapter Name***\> Transport Properties** dialog box.</span></span> <span data-ttu-id="4a442-104">AdapterHarness プロジェクトの XSD スキーマ ファイルで、これらのプロパティが定義されています。</span><span class="sxs-lookup"><span data-stu-id="4a442-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="4a442-105">構成スキーマの検証は、以下の 3 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="4a442-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="4a442-106">保存された構成を表示するときに、アダプター フレームワークは、保存された XML ドキュメントをスキーマに基づいて検証してからプロパティ ページに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4a442-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="4a442-107">フレームワークは、ドキュメントが有効ではない場合、構成スキーマ定義が変更されているものと見なします。</span><span class="sxs-lookup"><span data-stu-id="4a442-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="4a442-108">有効なドキュメントだけがプロパティ ページに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4a442-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="4a442-109">アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータのシリアル化から渡されます。</span><span class="sxs-lookup"><span data-stu-id="4a442-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="4a442-110">アダプターは、そのドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="4a442-110">The adapter then processes the document.</span></span> <span data-ttu-id="4a442-111">エラーがある場合は、フレームワークでキャッチされる例外が生成されて、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a442-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="4a442-112">不足している値または生成される値は、検証中に生成されます。</span><span class="sxs-lookup"><span data-stu-id="4a442-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="4a442-113">使用して、\<参照可能な表示 ="false"\>装飾エントリは非表示、プロパティ グリッドで場合でも、XML インスタンスの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a442-113">Using the \<browsable show="false"\> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="4a442-114">値をデータベースに格納する前に構成を保存すると、フレームワークはもう一度スキーマに基づいて XML ドキュメントを検証します。</span><span class="sxs-lookup"><span data-stu-id="4a442-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="4a442-115">これにより、有効なデータだけが維持されます。</span><span class="sxs-lookup"><span data-stu-id="4a442-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a442-116">参照</span><span class="sxs-lookup"><span data-stu-id="4a442-116">See Also</span></span>  
 [<span data-ttu-id="4a442-117">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="4a442-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)