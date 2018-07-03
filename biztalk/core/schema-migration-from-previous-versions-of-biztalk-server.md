---
title: BizTalk Server の以前のバージョンからのスキーマの移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54b9dba1ee759cd33f7f3db44553684c27b57d10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022464"
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a><span data-ttu-id="1279a-102">旧バージョンの BizTalk Server からのスキーマの移行</span><span class="sxs-lookup"><span data-stu-id="1279a-102">Schema Migration from Previous Versions of BizTalk Server</span></span>
<span data-ttu-id="1279a-103">このバージョンの BizTalk Server は XSD (XML Schema Definition) 言語を使用してメッセージ スキーマを表記しますが、旧バージョンは XDR (XML-Data Reduced) 構文を使用してメッセージ スキーマを表記していました。</span><span class="sxs-lookup"><span data-stu-id="1279a-103">This version of BizTalk Server uses XML Schema definition (XSD) language to represent message schemas, while previous versions used the XML-Data Reduced (XDR) syntax to represent message schemas.</span></span> <span data-ttu-id="1279a-104">旧バージョンの BizTalk Server からスキーマを移行する場合、XDR ではなく XSD を使用するようにスキーマを変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1279a-104">If you are migrating from a previous version of BizTalk Server, you must convert your schemas to use XSD rather than XDR.</span></span>  
  
 <span data-ttu-id="1279a-105">BizTalk スキーマを XDR 構文から XSD 構文に変換するには、次の作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="1279a-105">You need to perform the following tasks to convert a BizTalk schema from XDR syntax to XSD syntax:</span></span>  
  
- <span data-ttu-id="1279a-106">スキーマ ファイルの拡張子を .xdr から .xsd に変更します。</span><span class="sxs-lookup"><span data-stu-id="1279a-106">Change the extension of the schema file from.xdr to.xsd.</span></span>  
  
- <span data-ttu-id="1279a-107">名前を変更したスキーマを該当する BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="1279a-107">Add the renamed schema to the appropriate BizTalk project.</span></span>  
  
- <span data-ttu-id="1279a-108">BizTalk エディターで名前を変更したスキーマを開いて、XDR から XSD に変換します。</span><span class="sxs-lookup"><span data-stu-id="1279a-108">Convert the renamed schema from XDR to XSD by opening the schema in BizTalk Editor.</span></span>  
  
- <span data-ttu-id="1279a-109">スキーマを保存して、変換を永続的にします。</span><span class="sxs-lookup"><span data-stu-id="1279a-109">Make the conversion permanent by saving the schema.</span></span>  
  
  <span data-ttu-id="1279a-110">次の手順を実行する方法の詳細については、次を参照してください。 [XDR スキーマから XSD スキーマを移行する方法](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="1279a-110">For detailed information about how to perform these steps, see [How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1279a-111">参照</span><span class="sxs-lookup"><span data-stu-id="1279a-111">See Also</span></span>  
 <span data-ttu-id="1279a-112">[スキーマについて](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1279a-112">[About Schemas](../core/about-schemas.md) </span></span>  
 <span data-ttu-id="1279a-113">[XDR スキーマを XSD スキーマに移行する方法](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1279a-113">[How to Migrate XDR Schemas to XSD Schemas](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md) </span></span>  
 [<span data-ttu-id="1279a-114">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="1279a-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)