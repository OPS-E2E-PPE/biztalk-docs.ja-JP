---
title: オーケストレーションでマップを使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e67249857ec00b2ca66648c1985f0c336d93b3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255330"
---
# <a name="how-to-use-maps-in-orchestrations"></a><span data-ttu-id="9b8ac-102">オーケストレーションでマップを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9b8ac-102">How to Use Maps in Orchestrations</span></span>
<span data-ttu-id="9b8ac-103">BizTalk マッパーは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境内で動作するツールです。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-103">BizTalk Mapper is a tool that runs within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="9b8ac-104">BizTalk マッパーを使用することにより、リンクと Functoid で入力スキーマと出力スキーマの関係を定義したマップを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-104">You use BizTalk Mapper to create and edit maps in which you use links and functoids to define the relationship between an input and an output schema.</span></span> <span data-ttu-id="9b8ac-105">リンクは、レコードまたはフィールドのデータを直接コピーするような関係を定義するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-105">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="9b8ac-106">スキーマに含まれる項目どうしを直接接続したり、Functoid との接続を定義する場合にリンクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-106">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="9b8ac-107">Functoid は、複雑なデータ操作を実行するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-107">Functoids perform more complex data manipulations.</span></span>  
  
## <a name="examples-of-using-maps"></a><span data-ttu-id="9b8ac-108">マップの使用例</span><span class="sxs-lookup"><span data-stu-id="9b8ac-108">Examples of Using Maps</span></span>  
 <span data-ttu-id="9b8ac-109">マップを使用する方法を次のサンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-109">The following samples show ways in which you can use maps:</span></span>  
  
-   [<span data-ttu-id="9b8ac-110">XML ツール (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="9b8ac-110">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="9b8ac-111">PartyResolution (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9b8ac-111">PartyResolution (BizTalk Server Sample)</span></span>](../core/partyresolution-biztalk-server-sample.md)  
  
-   <span data-ttu-id="9b8ac-112">サンプルをダウンロードする SDK"を使用して、一括コピー Functoid から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-112">Download the SDK sample "Using the Mass Copy Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="9b8ac-113">SDK サンプル「ループ Functoid の使用」をダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-113">Download the SDK sample "Using the Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="9b8ac-114">サンプルをダウンロードする SDK「マッピング繰り返し構造への」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-114">Download the SDK sample "Mapping to a Repeating Structure" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="9b8ac-115">サンプルをダウンロードする SDK"テーブル ループ Functoid の使用"から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-115">Download the SDK sample "Using the Table Looping Functoid" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="9b8ac-116">「値のマッピングと値のマッピング (フラット化) Functoid を使用して」SDK サンプルからダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="9b8ac-116">Download the SDK sample "Using the Value Mapping and Value Mapping (Flattening) Functoids" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8ac-117">参照</span><span class="sxs-lookup"><span data-stu-id="9b8ac-117">See Also</span></span>  
 <span data-ttu-id="9b8ac-118">[BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="9b8ac-118">[Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="9b8ac-119">[メッセージの構築](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9b8ac-119">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 <span data-ttu-id="9b8ac-120">[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md) </span><span class="sxs-lookup"><span data-stu-id="9b8ac-120">[How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md) </span></span>  
 [<span data-ttu-id="9b8ac-121">メッセージを動的に変換する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="9b8ac-121">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)