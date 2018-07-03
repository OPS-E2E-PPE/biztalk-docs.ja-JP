---
title: Update2XMLSchema ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108bc63536e84dd18cd738fbc6ec10d1e07c404b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978139"
---
# <a name="update2xmlschema-tool"></a><span data-ttu-id="e5663-102">Update2XMLSchema ツール</span><span class="sxs-lookup"><span data-stu-id="e5663-102">Update2XMLSchema Tool</span></span>
<span data-ttu-id="e5663-103">Update2XMLSchema ツールでは、BizTalk エディターを操作する HL7 2. XML スキーマを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e5663-103">The Update2XMLSchema tool enables you to modify HL7 2.XML schemas to work with BizTalk Editor.</span></span> <span data-ttu-id="e5663-104">これは、Microsoft 内で特定の HL7 2. XML スキーマが正しく機能しないため[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]変更なし。</span><span class="sxs-lookup"><span data-stu-id="e5663-104">This is necessary because certain HL7 2.XML schemas do not work correctly within Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without modification.</span></span> <span data-ttu-id="e5663-105">スキーマを変更した後、ツールに置きます Schemas フォルダーで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]がインストールされている、たとえば、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk \<のバージョン\>HL7\Templates\Schemas のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="e5663-105">After modifying the schemas, the tool places them in the Schemas folder where [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] is installed, for instance, *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\Templates\Schemas.</span></span>  
  
 <span data-ttu-id="e5663-106">Update2XMLSchema ツールの実行結果のスキーマの一部のフィールドに手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5663-106">You need to update manually some fields of the schemas that result from running the Update2XMLSchema tool.</span></span> <span data-ttu-id="e5663-107">参照してください[手動更新のために必要な](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)それらのスキーマの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="e5663-107">See [Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) for a list of those schemas.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5663-108">構文</span><span class="sxs-lookup"><span data-stu-id="e5663-108">Syntax</span></span>  
 <span data-ttu-id="e5663-109">このツールにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\2XML ユーティリティのアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="e5663-109">This tool is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\2XML Utilities.</span></span> <span data-ttu-id="e5663-110">次のコマンドでコマンド プロンプトでは、このツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5663-110">You run this tool at the command prompt with the following command:</span></span>  
  
```  
Update2XMLSchema /s /v  
```  
  
 <span data-ttu-id="e5663-111">次の表は、このコマンドで使用するパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e5663-111">The following table lists the parameters to use with this command.</span></span>  
  
|<span data-ttu-id="e5663-112">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5663-112">Parameter</span></span>|<span data-ttu-id="e5663-113">名前</span><span class="sxs-lookup"><span data-stu-id="e5663-113">Name</span></span>|<span data-ttu-id="e5663-114">値</span><span class="sxs-lookup"><span data-stu-id="e5663-114">Value</span></span>|  
|---------------|----------|-----------|  
|<span data-ttu-id="e5663-115">*S*</span><span class="sxs-lookup"><span data-stu-id="e5663-115">*S*</span></span>|<span data-ttu-id="e5663-116">Source</span><span class="sxs-lookup"><span data-stu-id="e5663-116">Source</span></span>|<span data-ttu-id="e5663-117">元の HL7 スキーマの完全なパス</span><span class="sxs-lookup"><span data-stu-id="e5663-117">Full path of the original HL7 schemas</span></span>|  
|<span data-ttu-id="e5663-118">*V*</span><span class="sxs-lookup"><span data-stu-id="e5663-118">*V*</span></span>|<span data-ttu-id="e5663-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="e5663-119">Version</span></span>|<span data-ttu-id="e5663-120">2. XML スキーマのバージョン: 2.3.1、2.4、または 2.5</span><span class="sxs-lookup"><span data-stu-id="e5663-120">The version of the 2.XML schemas:  either 2.3.1, 2.4, or 2.5</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5663-121">例</span><span class="sxs-lookup"><span data-stu-id="e5663-121">Example</span></span>  
  
-   <span data-ttu-id="e5663-122">C:\231XML\v231\xsd ディレクトリにある version 2.3.1 2. XML スキーマを変更するは、コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5663-122">If you want to modify version 2.3.1 2.XML schemas located in the c:\231XML\v231\xsd directory, you would type the following command at the command prompt:</span></span>  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="e5663-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e5663-123">In This Section</span></span>  
  
-   [<span data-ttu-id="e5663-124">必要な手動更新</span><span class="sxs-lookup"><span data-stu-id="e5663-124">Required Manual Updates</span></span>](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)