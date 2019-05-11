---
title: スキーマの管理 |Microsoft Docs
description: BizTalk server での表示と非表示のプロパティを含むスキーマを使用する BizTalk 管理コンソールを使用して、XSD を表示、追跡を有効にします。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5632e79-b182-41c9-9138-eb88b44e3172
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c39d6bd414a1f9558e058881c41f6dd9bd1e5d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531145"
---
# <a name="manage-schemas"></a><span data-ttu-id="3beb1-103">スキーマを管理します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-103">Manage Schemas</span></span>

## <a name="overiew"></a><span data-ttu-id="3beb1-104">概要</span><span class="sxs-lookup"><span data-stu-id="3beb1-104">Overiew</span></span>
<span data-ttu-id="3beb1-105">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してスキーマを管理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage schemas.</span></span> <span data-ttu-id="3beb1-106">パイプラインおよびオーケストレーションはスキーマを使用して処理されるメッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-106">Schemas are used by pipelines and orchestrations to represent the message that will be processed.</span></span>  
  
 <span data-ttu-id="3beb1-107">スキーマは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で作成され、BizTalk アセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3beb1-107">Schemas are created in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="3beb1-108">スキーマを単独でアプリケーションに追加することはできません。スキーマは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3beb1-108">You cannot add a schema to an application individually; a schema is added to an application as follows:</span></span>  
  
- <span data-ttu-id="3beb1-109">」の説明に従って、アプリケーションに、スキーマを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-109">When you add a BizTalk assembly containing a schema to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="3beb1-110">」の説明に従って、スキーマを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-110">When you import an .msi file into an application that includes a BizTalk assembly containing a schema, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="3beb1-111">開発者が展開したときに、アプリケーションからスキーマを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-111">When a developer deploys into an application an assembly containing a schema from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="3beb1-112">スキーマの背景については、次を参照してください。[スキーマ](../core/schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-112">For background information about schemas, see [Schemas](../core/schemas.md).</span></span> <span data-ttu-id="3beb1-113">スキーマの開発方法の詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-113">For information about developing schemas, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3beb1-114">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="3beb1-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="3beb1-115">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3beb1-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="3beb1-116">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3beb1-116">Next steps</span></span> 
  
-   [<span data-ttu-id="3beb1-117">プロパティ スキーマを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="3beb1-117">Show and Hide Property Schemas</span></span>](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [<span data-ttu-id="3beb1-118">スキーマのスキーマ定義 (XSD) を表示する</span><span class="sxs-lookup"><span data-stu-id="3beb1-118">View the Schema Definition (XSD) of a Schema</span></span>](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [<span data-ttu-id="3beb1-119">スキーマの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="3beb1-119">Configure Tracking for a Schema</span></span>](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [<span data-ttu-id="3beb1-120">スキーマをアプリケーションから削除する</span><span class="sxs-lookup"><span data-stu-id="3beb1-120">Remove a Schema from an Application</span></span>](../core/how-to-remove-a-schema-from-an-application.md)