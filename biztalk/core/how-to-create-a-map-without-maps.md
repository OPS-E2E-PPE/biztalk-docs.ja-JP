---
title: マップなしのマップを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248794"
---
# <a name="how-to-create-a-map-without-maps"></a><span data-ttu-id="7a6ef-102">マップを使用しないでマップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7a6ef-102">How to Create a Map without Maps</span></span>
<span data-ttu-id="7a6ef-103">インスタンス メッセージを変換するための XSLT コードが既に手元にある場合は、マップを作成する代わりに、XSLT コードを使って直接データを変換できます。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-103">If you have XSLT code you have been using to convert instance messages, you can use that code directly instead of creating a map.</span></span>  
  
 <span data-ttu-id="7a6ef-104">空のマップを作成および設定は、XSLT コードを使用してその**カスタム XSLT パス**グリッド プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-104">Using your XSLT code involves creating an empty map and setting its **Custom XSLT Path** grid property.</span></span> <span data-ttu-id="7a6ef-105">XSLT コードでは、外部 .NET アセンブリを使用する場合は、カスタム拡張 XML ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-105">If your XSLT code uses external .NET assemblies, you also need to create a custom extension XML file.</span></span> <span data-ttu-id="7a6ef-106">カスタム拡張 XML ファイルの構造については、次を参照してください。、**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-106">For information about the structure of a custom extension XML file, see the **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a><span data-ttu-id="7a6ef-107">マップの代わりにカスタムの XSLT コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-107">Use custom XSLT code in place of a map</span></span>  
  
1.  <span data-ttu-id="7a6ef-108">空の BizTalk マップをプロジェクトに作成し、送信元スキーマおよび送信先スキーマを設定します。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-108">Create an empty BizTalk map in your project and set the source and destination schemas.</span></span>  
  
     <span data-ttu-id="7a6ef-109">マップを作成して、スキーマの設定については、次を参照してください。[マップの作成](../core/creating-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-109">For information about creating the map and setting the schemas, see [Creating Maps](../core/creating-maps.md).</span></span>  
  
2.  <span data-ttu-id="7a6ef-110">グリッド ビューで、マッパー グリッドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-110">In the Grid view, click the mapper grid.</span></span>  
  
     <span data-ttu-id="7a6ef-111">プロパティ ウィンドウの表示、**グリッド**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-111">The Properties window shows the **Grid** properties.</span></span>  
  
3.  <span data-ttu-id="7a6ef-112">[プロパティ] ウィンドウで選択**カスタム XSLT パス**、省略記号ボタンをクリックし、(**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-112">In the Properties window, select **Custom XSLT Path** and click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="7a6ef-113">**開く** ダイアログ ボックスで、ファイルに移動し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-113">In the **Open** dialog box, navigate to the file and click **Open**.</span></span>  
  
     <span data-ttu-id="7a6ef-114">**カスタム XSLT パス**プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-114">The **Custom XSLT Path** property is set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a6ef-115">BizTalk マッパーは XSLT 1.0 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-115">BizTalk Mapper supports XSLT 1.0 only.</span></span> <span data-ttu-id="7a6ef-116">XSLT 2.0 の使用は、BizTalk マッパーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a6ef-116">Using XSLT 2.0 in BizTalk Mapper is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6ef-117">参照</span><span class="sxs-lookup"><span data-stu-id="7a6ef-117">See Also</span></span>  
 <span data-ttu-id="7a6ef-118">[マップの概要](../core/about-maps.md) </span><span class="sxs-lookup"><span data-stu-id="7a6ef-118">[About Maps](../core/about-maps.md) </span></span>  
 <span data-ttu-id="7a6ef-119">[スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="7a6ef-119">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 [<span data-ttu-id="7a6ef-120">カスタム xslt は上書き</span><span class="sxs-lookup"><span data-stu-id="7a6ef-120">Custom XSLT</span></span>](../core/custom-xslt.md)   