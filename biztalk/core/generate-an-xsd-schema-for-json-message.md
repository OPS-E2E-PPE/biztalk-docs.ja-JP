---
title: "JSON メッセージの XSD スキーマの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b450c74f7d2eda6d3b688c40d0f8e8cde5c66d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-an-xsd-schema-for-json-message"></a><span data-ttu-id="2022d-102">JSON メッセージの XSD スキーマの生成</span><span class="sxs-lookup"><span data-stu-id="2022d-102">Generate an XSD schema for JSON message</span></span>
> [!NOTE]
>  <span data-ttu-id="2022d-103">このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2022d-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 <span data-ttu-id="2022d-104">このソリューションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリが JSON メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2022d-104">In this solution, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application receives a JSON message.</span></span> <span data-ttu-id="2022d-105">アプリがメッセージを処理する前に、メッセージを XSD スキーマに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2022d-105">Before the application can process the message, it must be converted to an XSD schema.</span></span> <span data-ttu-id="2022d-106">変換には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の JSON メッセージから XSD スキーマを作成する JSON スキーマ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="2022d-106">To do so, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a JSON Schema Wizard that creates an XSD schema from a JSON message.</span></span>  
  
1.  <span data-ttu-id="2022d-107">Visual Studio で、新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2022d-107">In Visual Studio, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="2022d-108">ソリューション エクスプ ローラーでプロジェクト名を右クリックして >**追加** > **新しい項目の** > **JSON スキーマ ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="2022d-108">In the Solution Explorer, right-click the project name > **Add** > **New Item** > **JSON Schema Wizard**.</span></span> <span data-ttu-id="2022d-109">スキーマの名前を指定 (`PO.xsd`) をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="2022d-109">Provide a name for the schema (`PO.xsd`), and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="2022d-110">JSON スキーマ ウィザードの [ようこそ] ページでをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="2022d-110">In the JSON Schema Wizard, on the welcome page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="2022d-111">JSON スキーマの情報ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリに送信される JSON 注文書ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="2022d-111">In the JSON Schema Information page, provide the location of the JSON purchase order file that is sent to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="2022d-112">ターゲットの名前空間のルート ノード名を指定し、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="2022d-112">Provide a root node name, a target namespace, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="2022d-113">![JSON の XSD スキーマを生成された](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span><span class="sxs-lookup"><span data-stu-id="2022d-113">![Generated XSD schema for JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span></span>  
  
5.  <span data-ttu-id="2022d-114">指定した名前のスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2022d-114">A schema with the specified name is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="2022d-115">生成されたスキーマ ファイル (**PO.xsd**) サンプルを使用しても用意されています。</span><span class="sxs-lookup"><span data-stu-id="2022d-115">The generated schema file (**PO.xsd**) is also provided with the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2022d-116">参照</span><span class="sxs-lookup"><span data-stu-id="2022d-116">See Also</span></span>  
 [<span data-ttu-id="2022d-117">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="2022d-117">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)