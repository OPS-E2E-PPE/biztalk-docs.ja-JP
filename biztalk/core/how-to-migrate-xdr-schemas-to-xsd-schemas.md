---
title: XDR スキーマを XSD スキーマに移行する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25971624"
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a><span data-ttu-id="30ed2-102">XDR スキーマを XSD スキーマに移行する方法</span><span class="sxs-lookup"><span data-stu-id="30ed2-102">How to Migrate XDR Schemas to XSD Schemas</span></span>
<span data-ttu-id="30ed2-103">以前のバージョンの BizTalk Server のスキーマを移行する場合、XDR (XML-Data Reduced) スキーマを XSD (XML Schema Definition) 言語スキーマに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30ed2-103">If you are migrating schemas from a previous version of BizTalk Server, you will need to convert your XML-Data Reduced (XDR) schemas into XML Schema definition (XSD) language schemas.</span></span> <span data-ttu-id="30ed2-104">このトピックでは、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="30ed2-104">This topic describes the necessary steps.</span></span>  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a><span data-ttu-id="30ed2-105">XDR スキーマから XSD スキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="30ed2-105">To generate an XSD schema from an XDR schema</span></span>  
  
1.  <span data-ttu-id="30ed2-106">**ソリューション エクスプ ローラー**, 、関連する BizTalk プロジェクトを右クリックし、順にポイント **追加**, 、クリックして **生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="30ed2-106">In **Solution Explorer**, right-click the relevant BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="30ed2-107">**生成項目の追加 - \< *BizTalk ProjectName* \>**  ] ダイアログ ボックスで、**テンプレート**セクションで、[**生成スキーマ**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="30ed2-107">In the **Add Generated Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="30ed2-108">**スキーマの生成** ダイアログ ボックスで、 **ドキュメントの種類** 一覧で、 **XDR スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="30ed2-108">In the **Generate Schemas** dialog box, in the **Document type** list, select **XDR Schema**.</span></span>  
  
4.  <span data-ttu-id="30ed2-109">をクリックして **参照**, 、クリックして、移行する XDR スキーマ ファイルを見つけます **OK**します。</span><span class="sxs-lookup"><span data-stu-id="30ed2-109">Click **Browse**, locate the XDR schema file you want to migrate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="30ed2-110">指定した XDR スキーマ ファイルから新しいスキーマが生成され、BizTalk エディターに表示されます。スキーマ名には、指定したファイルと同じ名前 (拡張子は .xsd) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="30ed2-110">A new schema is generated from the specified XDR schema file, using the same name as that file with the .xsd extension, and then opened in BizTalk Editor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30ed2-111">スキーマ ルート ノード名またはファイル名に対して、C# 予約語、.NET Framework 型、および名前空間名 (System など) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="30ed2-111">Avoid using C# reserved words and .NET Framework type and namespace names (such as System) as schema root node names or as file names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ed2-112">参照</span><span class="sxs-lookup"><span data-stu-id="30ed2-112">See Also</span></span>  
 <span data-ttu-id="30ed2-113">[プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="30ed2-113">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="30ed2-114">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="30ed2-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)