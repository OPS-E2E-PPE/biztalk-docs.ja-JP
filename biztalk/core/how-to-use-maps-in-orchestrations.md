---
title: オーケストレーションでマップを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd628d8-c163-431d-8ad7-d7d77007c549
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879b7a79db342ba7057cc4ff7a10efcf3c97fb62
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333440"
---
# <a name="how-to-use-maps-in-orchestrations"></a><span data-ttu-id="e9f7c-102">オーケストレーションでマップを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e9f7c-102">How to Use Maps in Orchestrations</span></span>
<span data-ttu-id="e9f7c-103">BizTalk マッパーは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境内で動作するツールです。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="e9f7c-104">作成および使用するリンクおよび functoid の入力と出力スキーマ間のリレーションシップを定義するマップを編集するには、BizTalk マッパーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-104">You use BizTalk Mapper to create and edit maps in which you use links and functoids to define the relationship between an input and an output schema.</span></span> <span data-ttu-id="e9f7c-105">リンクは、レコードまたはフィールドのデータを直接コピーするような関係を定義するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-105">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="e9f7c-106">スキーマに含まれる項目どうしを直接接続したり、Functoid との接続を定義する場合にリンクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-106">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="e9f7c-107">Functoid より複雑なデータ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-107">Functoids perform more complex data manipulations.</span></span>  
  
## <a name="examples-of-using-maps"></a><span data-ttu-id="e9f7c-108">マップの使用例</span><span class="sxs-lookup"><span data-stu-id="e9f7c-108">Examples of Using Maps</span></span>  
 <span data-ttu-id="e9f7c-109">次のサンプルでは、マップを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-109">The following samples show ways in which you can use maps:</span></span>  
  
-   [<span data-ttu-id="e9f7c-110">XML ツール (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e9f7c-110">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e9f7c-111">PartyResolution (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e9f7c-111">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="e9f7c-112">SDK サンプルの「一括コピー Functoid の使用」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-112">Download the SDK sample "Using the Mass Copy Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e9f7c-113">SDK サンプル「ループ Functoid の使用」をダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-113">Download the SDK sample "Using the Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e9f7c-114">「マッピング繰り返し構造への」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-114">Download the SDK sample "Mapping to a Repeating Structure" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e9f7c-115">"テーブル ループ Functoid の使用"SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-115">Download the SDK sample "Using the Table Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e9f7c-116">「値のマッピングと値のマッピング (フラット化) Functoid を使用して」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="e9f7c-116">Download the SDK sample "Using the Value Mapping and Value Mapping (Flattening) Functoids" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f7c-117">参照</span><span class="sxs-lookup"><span data-stu-id="e9f7c-117">See Also</span></span>  
 <span data-ttu-id="e9f7c-118">[BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="e9f7c-118">[Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="e9f7c-119">[メッセージの構築](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e9f7c-119">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 <span data-ttu-id="e9f7c-120">[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md) </span><span class="sxs-lookup"><span data-stu-id="e9f7c-120">[How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md) </span></span>  
 [<span data-ttu-id="e9f7c-121">メッセージに動的に変換する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="e9f7c-121">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)