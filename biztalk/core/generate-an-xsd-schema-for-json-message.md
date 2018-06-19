---
title: JSON メッセージの XSD スキーマの生成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88caf75d312179cd45bb1b3b421d6c2c7f25c2a8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007483"
---
# <a name="generate-an-xsd-schema-for-json-message"></a><span data-ttu-id="357d4-102">JSON メッセージの XSD スキーマの生成</span><span class="sxs-lookup"><span data-stu-id="357d4-102">Generate an XSD schema for JSON message</span></span>
> [!NOTE]
>  <span data-ttu-id="357d4-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="357d4-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="357d4-104">このソリューションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリが JSON メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="357d4-104">In this solution, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application receives a JSON message.</span></span> <span data-ttu-id="357d4-105">アプリがメッセージを処理する前に、メッセージを XSD スキーマに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357d4-105">Before the application can process the message, it must be converted to an XSD schema.</span></span> <span data-ttu-id="357d4-106">変換には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の JSON メッセージから XSD スキーマを作成する JSON スキーマ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="357d4-106">To do so, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a JSON Schema Wizard that creates an XSD schema from a JSON message.</span></span>  
  
1.  <span data-ttu-id="357d4-107">Visual Studio で、新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="357d4-107">In Visual Studio, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="357d4-108">ソリューション エクスプ ローラーでプロジェクト名を右クリックして >**追加** > **新しい項目の** > **JSON スキーマ ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="357d4-108">In the Solution Explorer, right-click the project name > **Add** > **New Item** > **JSON Schema Wizard**.</span></span> <span data-ttu-id="357d4-109">スキーマの名前を指定 (`PO.xsd`) をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="357d4-109">Provide a name for the schema (`PO.xsd`), and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="357d4-110">JSON スキーマ ウィザードの [ようこそ] ページでをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="357d4-110">In the JSON Schema Wizard, on the welcome page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="357d4-111">JSON スキーマの情報ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリに送信される JSON 注文書ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="357d4-111">In the JSON Schema Information page, provide the location of the JSON purchase order file that is sent to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="357d4-112">ターゲットの名前空間のルート ノード名を指定し、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="357d4-112">Provide a root node name, a target namespace, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="357d4-113">![JSON の XSD スキーマを生成された](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span><span class="sxs-lookup"><span data-stu-id="357d4-113">![Generated XSD schema for JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span></span>  
  
5.  <span data-ttu-id="357d4-114">指定した名前のスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="357d4-114">A schema with the specified name is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="357d4-115">生成されたスキーマ ファイル (**PO.xsd**) サンプルを使用しても用意されています。</span><span class="sxs-lookup"><span data-stu-id="357d4-115">The generated schema file (**PO.xsd**) is also provided with the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357d4-116">参照</span><span class="sxs-lookup"><span data-stu-id="357d4-116">See Also</span></span>  
 [<span data-ttu-id="357d4-117">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="357d4-117">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)