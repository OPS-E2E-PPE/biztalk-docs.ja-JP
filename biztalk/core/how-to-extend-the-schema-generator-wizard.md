---
title: スキーマ生成ウィザードを拡張する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Schema Generator Wizard
- Schema Generator Wizard
ms.assetid: ea4b5532-f904-4da0-9612-e092e7e4edc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6fb901186dddf69a94fca4467b543f047c27719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013811"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a><span data-ttu-id="ea8d3-102">スキーマ生成ウィザードを拡張する方法</span><span class="sxs-lookup"><span data-stu-id="ea8d3-102">How to Extend the Schema Generator Wizard</span></span>
<span data-ttu-id="ea8d3-103">スキーマの生成用の新規作成ウィザードを作成する方法と、既存のスキーマ生成ウィザードを拡張する方法。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-103">How to extend the existing Schema Generator Wizard and how to create a new wizard for schema generation.</span></span>  
  
## <a name="extend-the-existing-schema-wizard"></a><span data-ttu-id="ea8d3-104">既存のスキーマ ウィザードを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-104">Extend the existing schema wizard</span></span>  
  
1. <span data-ttu-id="ea8d3-105">既存のスキーマ生成ウィザードに統合できる新しいスキーマ生成モジュールを作成する ISchemaGenerator インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-105">Implement the ISchemaGenerator interface to create a new schema generator module that you can integrate into the existing Schema Generator Wizard.</span></span>  
  
   ```  
   public interface ISchemaGenerator  
   {  
   //Method to extract a schema from a document.  
   void GenerateSchema(string inputDocument,string outputDocumentPath);  
  
   //Method to extract the errors.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Errors();  
  
   //Method to extract the warnings.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Warnings();  
  
   //Method to extract the referenced schemas.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] ReferencedSchemas();  
   }  
   ```  
  
2. <span data-ttu-id="ea8d3-106">次の Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに、結果として得られるアセンブリをドロップします。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-106">Drop the resulting assembly in the following Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ea8d3-107">\Developer Tools\Schema エディター拡張機能</span><span class="sxs-lookup"><span data-stu-id="ea8d3-107">\Developer Tools\Schema Editor Extensions</span></span>  
  
    <span data-ttu-id="ea8d3-108">次にスキーマ生成ウィザードを実行すると、新しいスキーマ生成モジュールが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-108">The next time you run the Schema Generator Wizard, it will automatically pick up your new schema generator module.</span></span>  
  
   <span data-ttu-id="ea8d3-109">新しいスキーマ ウィザードを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-109">Use the following procedure to create a new schema wizard.</span></span>  
  
   <span data-ttu-id="ea8d3-110">**SDK の場所**</span><span class="sxs-lookup"><span data-stu-id="ea8d3-110">**Location in SDK**</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ea8d3-111">\SDK\Utilities\Schema generator</span><span class="sxs-lookup"><span data-stu-id="ea8d3-111">\SDK\Utilities\Schema Generator</span></span>  
  
### <a name="create-a-new-schema-wizard"></a><span data-ttu-id="ea8d3-112">新しいスキーマ ウィザードを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-112">Create a new schema wizard</span></span>  
  
1. <span data-ttu-id="ea8d3-113">InstallDTD.vbs を Microsoft.BizTalk.DTDToXSDGenerator.dll のインストールを実行して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-113">Run InstallDTD.vbs to install Microsoft.BizTalk.DTDToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="ea8d3-114">DTDToXSDGenerator.dll は、DTD ファイルを XSD に変換するために使用できるクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-114">DTDToXSDGenerator.dll exposes classes you can use to convert DTD files to XSD.</span></span>  
  
2. <span data-ttu-id="ea8d3-115">InstallWFX.vbs を Microsoft.BizTalk.WFXToXSDGenerator.dll のインストールを実行して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-115">Run InstallWFX.vbs to install Microsoft.BizTalk.WFXToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="ea8d3-116">WFXToXSDGenerator.dll は、WFX ファイルを XSD に変換するために使用できるクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-116">WFXToXSDGenerator.dll exposes classes you can use to convert WFX files to XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8d3-117">参照</span><span class="sxs-lookup"><span data-stu-id="ea8d3-117">See Also</span></span>  
 [<span data-ttu-id="ea8d3-118">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ea8d3-118">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)