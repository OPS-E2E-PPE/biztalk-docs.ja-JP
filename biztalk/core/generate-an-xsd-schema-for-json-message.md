---
title: JSON メッセージの XSD スキーマの生成 |Microsoft Docs
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
ms.openlocfilehash: 1f44b18593e756fe1ed6e05e03d62e498f66c0a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387769"
---
# <a name="generate-an-xsd-schema-for-json-message"></a><span data-ttu-id="0861b-102">JSON メッセージの XSD スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0861b-102">Generate an XSD schema for JSON message</span></span>
> [!NOTE]
>  <span data-ttu-id="0861b-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0861b-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="0861b-104">このソリューションで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション JSON メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0861b-104">In this solution, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application receives a JSON message.</span></span> <span data-ttu-id="0861b-105">アプリケーションでは、メッセージを処理できますが、前に、XSD スキーマに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0861b-105">Before the application can process the message, it must be converted to an XSD schema.</span></span> <span data-ttu-id="0861b-106">これを行うに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]JSON メッセージから XSD スキーマを作成する JSON スキーマ ウィザードを提供します。</span><span class="sxs-lookup"><span data-stu-id="0861b-106">To do so, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a JSON Schema Wizard that creates an XSD schema from a JSON message.</span></span>  
  
1. <span data-ttu-id="0861b-107">Visual Studio で、作成、新しい[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="0861b-107">In Visual Studio, create a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2. <span data-ttu-id="0861b-108">ソリューション エクスプ ローラーでプロジェクト名を右クリックして >**追加** > **新しい項目の** > **JSON スキーマ ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="0861b-108">In the Solution Explorer, right-click the project name > **Add** > **New Item** > **JSON Schema Wizard**.</span></span> <span data-ttu-id="0861b-109">スキーマの名前を指定 (`PO.xsd`)、をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0861b-109">Provide a name for the schema (`PO.xsd`), and then click **Add**.</span></span>  
  
3. <span data-ttu-id="0861b-110">JSON スキーマ ウィザードの [ようこそ] ページで、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="0861b-110">In the JSON Schema Wizard, on the welcome page, click **Next**.</span></span>  
  
4. <span data-ttu-id="0861b-111">JSON スキーマ情報 ページに送信される JSON 注文書順序ファイルの場所を指定します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="0861b-111">In the JSON Schema Information page, provide the location of the JSON purchase order file that is sent to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="0861b-112">ターゲットの名前空間のルート ノード名を指定し、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="0861b-112">Provide a root node name, a target namespace, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="0861b-113">![JSON の生成された XSD スキーマ](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span><span class="sxs-lookup"><span data-stu-id="0861b-113">![Generated XSD schema for JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")</span></span>  
  
5. <span data-ttu-id="0861b-114">指定した名前のスキーマが追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="0861b-114">A schema with the specified name is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="0861b-115">生成されたスキーマ ファイル (**PO.xsd**) サンプルを使用しても提供されます。</span><span class="sxs-lookup"><span data-stu-id="0861b-115">The generated schema file (**PO.xsd**) is also provided with the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0861b-116">参照</span><span class="sxs-lookup"><span data-stu-id="0861b-116">See Also</span></span>  
 [<span data-ttu-id="0861b-117">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="0861b-117">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)