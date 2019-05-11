---
title: XDR スキーマを XSD スキーマに移行する方法 |Microsoft Docs
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
ms.openlocfilehash: ee5394b0a4b761e1dc650cfa41e10822d856895a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384641"
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a><span data-ttu-id="c79fc-102">XDR スキーマを XSD スキーマに移行する方法</span><span class="sxs-lookup"><span data-stu-id="c79fc-102">How to Migrate XDR Schemas to XSD Schemas</span></span>
<span data-ttu-id="c79fc-103">BizTalk Server の以前のバージョンからスキーマを移行する場合は、Xml-data Reduced (XDR) スキーマを XML スキーマ定義 (XSD) 言語スキーマに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79fc-103">If you are migrating schemas from a previous version of BizTalk Server, you will need to convert your XML-Data Reduced (XDR) schemas into XML Schema definition (XSD) language schemas.</span></span> <span data-ttu-id="c79fc-104">このトピックでは、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c79fc-104">This topic describes the necessary steps.</span></span>  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a><span data-ttu-id="c79fc-105">XDR スキーマから XSD スキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="c79fc-105">To generate an XSD schema from an XDR schema</span></span>  
  
1.  <span data-ttu-id="c79fc-106">**ソリューション エクスプ ローラー**、関連する BizTalk プロジェクトを右クリックし、 をポイント**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="c79fc-106">In **Solution Explorer**, right-click the relevant BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c79fc-107">**生成項目の追加 - \< *BizTalk ProjectName* \>**   ダイアログ ボックスで、**テンプレート**セクションで、**生成スキーマ**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c79fc-107">In the **Add Generated Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="c79fc-108">**スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[ **XDR スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="c79fc-108">In the **Generate Schemas** dialog box, in the **Document type** list, select **XDR Schema**.</span></span>  
  
4.  <span data-ttu-id="c79fc-109">をクリックして**参照**、クリックして、移行する XDR スキーマ ファイルを見つけます**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c79fc-109">Click **Browse**, locate the XDR schema file you want to migrate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c79fc-110">新しいスキーマは、指定した XDR スキーマ ファイル、したファイル拡張子は .xsd と同じ名前を使用して、BizTalk エディターで開かれたから生成されます。</span><span class="sxs-lookup"><span data-stu-id="c79fc-110">A new schema is generated from the specified XDR schema file, using the same name as that file with the .xsd extension, and then opened in BizTalk Editor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c79fc-111">使用しないでくださいC#スキーマ ルート ノード名、またはファイル名として単語や .NET Framework 型と名前空間の名前 (System など) に予約されています。</span><span class="sxs-lookup"><span data-stu-id="c79fc-111">Avoid using C# reserved words and .NET Framework type and namespace names (such as System) as schema root node names or as file names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79fc-112">参照</span><span class="sxs-lookup"><span data-stu-id="c79fc-112">See Also</span></span>  
 <span data-ttu-id="c79fc-113">[プロジェクト内のスキーマを管理します。](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="c79fc-113">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="c79fc-114">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="c79fc-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)