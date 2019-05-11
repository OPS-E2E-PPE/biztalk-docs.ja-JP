---
title: スキーマの検証 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2a90b0b707b9ab037968f7636d75437a43d1a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279600"
---
# <a name="validating-a-schema-edi"></a><span data-ttu-id="03071-102">スキーマの検証 (EDI)</span><span class="sxs-lookup"><span data-stu-id="03071-102">Validating a Schema (EDI)</span></span>
<span data-ttu-id="03071-103">デザイン時に EDI スキーマを検証できます。</span><span class="sxs-lookup"><span data-stu-id="03071-103">You can validate an EDI schema at design time.</span></span> <span data-ttu-id="03071-104">それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。</span><span class="sxs-lookup"><span data-stu-id="03071-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="03071-105">スキーマの検証操作では、EDI ルールに基づいてスキーマの検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="03071-105">The validate-schema operation validates the schema based on EDI rules.</span></span> <span data-ttu-id="03071-106">スキーマを検証するために入力メッセージ インスタンスを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="03071-106">You do not have to designate an input message instance to validate a schema.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="03071-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="03071-107">Prerequisites</span></span>  
 <span data-ttu-id="03071-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03071-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-schema"></a><span data-ttu-id="03071-109">スキーマを検証するには</span><span class="sxs-lookup"><span data-stu-id="03071-109">To validate a schema</span></span>  
  
1. <span data-ttu-id="03071-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="03071-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="03071-111">ソリューション エクスプローラーで、検証するメッセージ スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="03071-111">To the project in Solution Explorer, add the message schema that you want to validate.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="03071-112">メッセージ スキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder フォルダーの下の該当するサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="03071-112">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="03071-113">スキーマ ファイルをインストールする方法の詳細については、次を参照してください。 [EDI スキーマ ファイルをインストールする方法](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)します。</span><span class="sxs-lookup"><span data-stu-id="03071-113">For information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="03071-114">スキーマを検証するためにプロジェクトをビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="03071-114">You do not have to build the project to validate a schema.</span></span>  
  
2. <span data-ttu-id="03071-115">ソリューション エクスプ ローラーでスキーマを右クリックし、をクリックし、**スキーマの検証**です。</span><span class="sxs-lookup"><span data-stu-id="03071-115">Right-click the schema in Solution Explorer, and then click **Validate Schema**.</span></span>  
  
3. <span data-ttu-id="03071-116">操作が成功したことを示すメッセージが [出力] ウィンドウに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03071-116">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03071-117">参照</span><span class="sxs-lookup"><span data-stu-id="03071-117">See Also</span></span>  
 [<span data-ttu-id="03071-118">デザイン時 XML ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="03071-118">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)