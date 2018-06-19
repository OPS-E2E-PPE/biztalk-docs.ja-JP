---
title: 別のアグリーメント プロパティの再利用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7db2118f372014a3e8f108c1ff2273bc5aad976
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007428"
---
# <a name="reusing-properties-from-another-agreement"></a><span data-ttu-id="bab7f-102">別のアグリーメントのプロパティの再利用</span><span class="sxs-lookup"><span data-stu-id="bab7f-102">Reusing Properties from Another Agreement</span></span>
<span data-ttu-id="bab7f-103">プロパティはアグリーメント間で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-103">You can reuse properties between agreements.</span></span> <span data-ttu-id="bab7f-104">これにより、新しいアグリーメントのプロパティのほとんどまたはすべてが、既存のアグリーメントのプロパティと同じ場合には、時間を大幅に節約することができます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-104">This can save a significant amount of time when either most or all of the properties of a new agreement are the same as those of an existing agreement.</span></span> <span data-ttu-id="bab7f-105">[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server でのユーザー インターフェイスでは、アグリーメントを XML テンプレート ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-105">The [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] user interface in BizTalk Server enables you to export an agreement into an XML template file.</span></span> <span data-ttu-id="bab7f-106">次に、XML テンプレートをインポートして、アグリーメントの同じプロパティを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-106">You can then import the XML template to reuse the same agreement properties.</span></span>  
  
 <span data-ttu-id="bab7f-107">アグリーメントを XML テンプレートにエクスポートすると、すべてではないものの、アグリーメントのほとんどのプロパティが取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-107">Exporting the agreement to an XML template captures most, but not all, properties from the agreement.</span></span> <span data-ttu-id="bab7f-108">以下のプロパティは*いない*XML テンプレート ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bab7f-108">The following properties will *not* be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="bab7f-109">すべてのプロパティ、**全般プロパティ** ページで、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="bab7f-109">All the properties from the **General Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bab7f-110">すべてのプロパティを**連絡先** ページで、**全般** タブ。</span><span class="sxs-lookup"><span data-stu-id="bab7f-110">All the properties from the **Contacts** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bab7f-111">すべてのプロパティを**追加のプロパティ** ページで、**全般** タブ。</span><span class="sxs-lookup"><span data-stu-id="bab7f-111">All the properties from the **Additional Properties** page in the **General** tab.</span></span>  
  
-   <span data-ttu-id="bab7f-112">識別子関連の設定から、**識別子**一方向アグリーメント タブのページでします。これらの設定は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bab7f-112">Identifier-related settings from the **Identifiers** page in the one-way agreement tab. These are:</span></span>  
  
    -   <span data-ttu-id="bab7f-113">**X12**: ISA5、ISA6、ISA7、ISA8、およびその他のアグリーメント リゾルバーの設定</span><span class="sxs-lookup"><span data-stu-id="bab7f-113">**For X12**: ISA5, ISA6, ISA7, ISA8, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="bab7f-114">**Edifact**: UNB 2.1、UNB 2.2、UNB 3.1、UNB 3.2、およびその他のアグリーメント リゾルバーの設定</span><span class="sxs-lookup"><span data-stu-id="bab7f-114">**For EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2, and additional agreement resolver settings</span></span>  
  
    -   <span data-ttu-id="bab7f-115">**AS2 の**: AS2-には、AS2-、およびその他のアグリーメント リゾルバーの設定</span><span class="sxs-lookup"><span data-stu-id="bab7f-115">**For AS2**: AS2-To, AS2-From, and additional agreement resolver settings</span></span>  
  
-   <span data-ttu-id="bab7f-116">送信ポートの関連付け、**送信ポート**契約の X12、EDIFACT、および AS2 の一方向アグリーメント タブのページです。</span><span class="sxs-lookup"><span data-stu-id="bab7f-116">Send port association from the **Send Ports** page in the one-way agreement tab for X12, EDIFACT, and AS2 agreements.</span></span>  
  
 <span data-ttu-id="bab7f-117">上記に示したプロパティ以外の、次のプロパティは XML テンプレート ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-117">Other than the properties listed above, the following properties will be exported to the XML template file:</span></span>  
  
-   <span data-ttu-id="bab7f-118">エンコード プロトコル関連のすべての設定 (X12、EDIFACT、または AS2)。</span><span class="sxs-lookup"><span data-stu-id="bab7f-118">All settings related to the encoding protocol (X12, EDIFACT, or AS2).</span></span>  
  
-   <span data-ttu-id="bab7f-119">バッチ関連のすべての設定 (バッチ ID を除く)。</span><span class="sxs-lookup"><span data-stu-id="bab7f-119">All the batch-related settings (other than the batch ID).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bab7f-120">適用できるすべてのプロパティは、コピー先のアグリーメントにプロパティをコピーしたときに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="bab7f-120">All the applicable properties will be overwritten when you copy properties to the destination agreement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bab7f-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bab7f-121">In This Section</span></span>  
  
-   [<span data-ttu-id="bab7f-122">XML ファイルへのアグリーメント プロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="bab7f-122">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [<span data-ttu-id="bab7f-123">XML ファイルからのアグリーメント プロパティのインポート</span><span class="sxs-lookup"><span data-stu-id="bab7f-123">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="bab7f-124">参照</span><span class="sxs-lookup"><span data-stu-id="bab7f-124">See Also</span></span>  
 [<span data-ttu-id="bab7f-125">EDI のプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="bab7f-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)