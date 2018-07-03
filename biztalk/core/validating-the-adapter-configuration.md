---
title: アダプター構成の検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7fa3af1fa0116f859f0d3f39f2235be38cbc0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008131"
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="0c9da-102">アダプターの構成情報の検証</span><span class="sxs-lookup"><span data-stu-id="0c9da-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="0c9da-103">受信場所と送信ポートを追加すると、中に求められますのカスタム プロパティを構成する、 **\<**<em>アダプター名</em> **\>トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0c9da-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<**<em>Adapter Name</em>**\> Transport Properties** dialog box.</span></span> <span data-ttu-id="0c9da-104">AdapterHarness プロジェクトの XSD スキーマ ファイルで、これらのプロパティが定義されています。</span><span class="sxs-lookup"><span data-stu-id="0c9da-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="0c9da-105">構成スキーマの検証は、以下の 3 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="0c9da-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="0c9da-106">保存された構成を表示するときに、アダプター フレームワークは、保存された XML ドキュメントをスキーマに基づいて検証してからプロパティ ページに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="0c9da-107">フレームワークは、ドキュメントが有効ではない場合、構成スキーマ定義が変更されているものと見なします。</span><span class="sxs-lookup"><span data-stu-id="0c9da-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="0c9da-108">有効なドキュメントだけがプロパティ ページに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="0c9da-109">アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータをシリアル化から渡されます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="0c9da-110">アダプターは、そのドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="0c9da-110">The adapter then processes the document.</span></span> <span data-ttu-id="0c9da-111">エラーがある場合は、フレームワークでキャッチされる例外が生成されて、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="0c9da-112">不足している値または生成される値は、検証中に生成されます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="0c9da-113">使用して、\<ブラウズ show ="false"\>装飾が XML インスタンスに値が表示されますが、プロパティ グリッド内のエントリを表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="0c9da-113">Using the \<browsable show="false"\> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="0c9da-114">値をデータベースに格納する前に構成を保存すると、フレームワークはもう一度スキーマに基づいて XML ドキュメントを検証します。</span><span class="sxs-lookup"><span data-stu-id="0c9da-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="0c9da-115">これにより、有効なデータだけが維持されます。</span><span class="sxs-lookup"><span data-stu-id="0c9da-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c9da-116">参照</span><span class="sxs-lookup"><span data-stu-id="0c9da-116">See Also</span></span>  
 [<span data-ttu-id="0c9da-117">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="0c9da-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)