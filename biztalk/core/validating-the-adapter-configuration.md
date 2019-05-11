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
ms.openlocfilehash: cc36a885614eac72f70e588fefe4731717322019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279537"
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="b6bb4-102">アダプター構成の検証</span><span class="sxs-lookup"><span data-stu-id="b6bb4-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="b6bb4-103">受信場所と送信ポートを追加すると、中に求められますのカスタム プロパティを構成する、 **\<**<em>アダプター名</em> **\>トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<**<em>Adapter Name</em>**\> Transport Properties** dialog box.</span></span> <span data-ttu-id="b6bb4-104">AdapterHarness プロジェクトの XSD スキーマ ファイルは、これらのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="b6bb4-105">3 つの部分で構成スキーマの検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="b6bb4-106">保存された構成を表示するときに、アダプター フレームワークは、プロパティ ページに、ドキュメントを読み込む前にスキーマの保存された XML ドキュメントを検証します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="b6bb4-107">フレームワークでは、無効なドキュメントが構成のスキーマ定義の変更を示すことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="b6bb4-108">有効なドキュメントだけが、プロパティ ページに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="b6bb4-109">アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータをシリアル化から渡されます。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="b6bb4-110">アダプターは、ドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-110">The adapter then processes the document.</span></span> <span data-ttu-id="b6bb4-111">エラーは、フレームワークでキャッチして、ユーザーに表示される例外を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="b6bb4-112">検証中に、不足しているまたは生成された値を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="b6bb4-113">使用して、\<ブラウズ show ="false"\>装飾が XML インスタンスに値が表示されますが、プロパティ グリッド内のエントリを表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-113">Using the \<browsable show="false"\> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="b6bb4-114">値をデータベースに配置する前に、構成を保存するときに、フレームワークはもう一度スキーマに対して XML ドキュメントを検証します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="b6bb4-115">これにより、唯一の有効なデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="b6bb4-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6bb4-116">参照</span><span class="sxs-lookup"><span data-stu-id="b6bb4-116">See Also</span></span>  
 [<span data-ttu-id="b6bb4-117">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="b6bb4-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)