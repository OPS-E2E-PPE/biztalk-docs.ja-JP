---
title: 新しい Partner Interface Process の組み込み |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2c372adb1993aacee1ba2d56d8a5dc2f8d9d0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283556"
---
# <a name="incorporating-a-new-partner-interface-process"></a><span data-ttu-id="52508-102">新しい Partner Interface Process の組み込み</span><span class="sxs-lookup"><span data-stu-id="52508-102">Incorporating a New Partner Interface Process</span></span>
<span data-ttu-id="52508-103">新しい RosettaNet Partner インターフェイス Process (PIP) スキーマ Microsoft® を組み込むことができます[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="52508-103">You can incorporate a new RosettaNet Partner Interface Process (PIP) schema in Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] assemblies.</span></span> <span data-ttu-id="52508-104">次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="52508-104">You do so by:</span></span>  
  
- <span data-ttu-id="52508-105">RosettaNet の Web サイトから PIP スキーマをダウンロード[ http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)します。</span><span class="sxs-lookup"><span data-stu-id="52508-105">Downloading the PIP schema from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
- <span data-ttu-id="52508-106">このスキーマを、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] RNPIP アセンブリまたは別の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] アセンブリの一部として [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に展開します。</span><span class="sxs-lookup"><span data-stu-id="52508-106">Deploying the schema to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as part of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly or as part of a separate [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] assembly.</span></span> <span data-ttu-id="52508-107">詳細については、次を参照してください。[新しい PIP による BTARN の拡張](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)します。</span><span class="sxs-lookup"><span data-stu-id="52508-107">For more information, see [Extending BTARN with a New PIP](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).</span></span>  
  
- <span data-ttu-id="52508-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで新しいプロセス構成設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="52508-108">Creating a new Process Configuration Setting in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="52508-109">詳細については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="52508-109">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
  <span data-ttu-id="52508-110">ダウンロードしたスキーマは通常は .dtd 形式で、RosettaNet 組織の PIP 仕様が .doc ファイルとして添付されています。</span><span class="sxs-lookup"><span data-stu-id="52508-110">The downloaded schema is generally in .dtd format, with an accompanying PIP specification from the RosettaNet organization as a .doc file.</span></span> <span data-ttu-id="52508-111">パイプラインが新しいスキーマを使用するように拡張するプロセスで、PIP の .dtd ファイルを .xsd ファイルに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52508-111">The process of extending the pipeline to use the new schema includes converting the PIP .dtd file into an .xsd file.</span></span>  
  
  <span data-ttu-id="52508-112">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] をインストールするときに、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK に複数の XSD スキーマもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="52508-112">When you install [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a number of XSD schemas.</span></span> <span data-ttu-id="52508-113">これらのスキーマを見つけることができます、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas フォルダー。</span><span class="sxs-lookup"><span data-stu-id="52508-113">You can find those schemas in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas folder.</span></span> <span data-ttu-id="52508-114">BTARN がこれらのスキーマを RNPIPs.dll ファイルにビルドします。</span><span class="sxs-lookup"><span data-stu-id="52508-114">BTARN builds these schemas into an RNPIPs.dll file.</span></span> <span data-ttu-id="52508-115">スキーマを変更する必要がある場合は、同じフォルダーで RNPIP のプロジェクトを開き、BizTalk エディターで変更してから、アセンブリを再コンパイルして再展開します。</span><span class="sxs-lookup"><span data-stu-id="52508-115">If you have to change one of these schemas, you must open the RNPIPs project in the same folder, change the schema in BizTalk Editor, and then recompile and redeploy the assembly.</span></span> <span data-ttu-id="52508-116">RNPIP の .dll ファイルを再展開したら、そのスキーマを使用するパイプラインを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52508-116">After you redeploy the RNPIPs.dll file, you must redeploy the pipeline that uses the schema.</span></span> <span data-ttu-id="52508-117">このプロセスを使用すると、新しいスキーマを BTARN に組み込むことができますが、パイプラインを拡張して新しいスキーマを含める方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="52508-117">You could use this process to incorporate a new schema in BTARN, but it is easier to extend the pipeline to include the new schema.</span></span>  
  
### <a name="to-obtain-the-pip-schema"></a><span data-ttu-id="52508-118">PIP スキーマを取得するには</span><span class="sxs-lookup"><span data-stu-id="52508-118">To obtain the PIP schema</span></span>  
  
-   <span data-ttu-id="52508-119">Internet Explorer で RosettaNet の Web サイトに移動します。 [ http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)します。</span><span class="sxs-lookup"><span data-stu-id="52508-119">In Internet Explorer, go to the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52508-120">参照</span><span class="sxs-lookup"><span data-stu-id="52508-120">See Also</span></span>  
 [<span data-ttu-id="52508-121">新しい PIP による BTARN の拡張</span><span class="sxs-lookup"><span data-stu-id="52508-121">Extending BTARN with a New PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)