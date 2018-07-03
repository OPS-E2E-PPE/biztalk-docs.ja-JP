---
title: アプリケーションまたはグループ内で一意にする必要がある成果物 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb81ffe1f97681f82ddc3d45b9d93ff34b5e172a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023264"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a><span data-ttu-id="e9851-102">アプリケーションまたはグループ内で一意である必要があるアイテム</span><span class="sxs-lookup"><span data-stu-id="e9851-102">Artifacts That Must Be Unique in an Application or Group</span></span>
<span data-ttu-id="e9851-103">次に示すように、BizTalk グループまたはアプリケーション内の特定の種類のアイテムは一意であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9851-103">Certain types of artifacts in a BizTalk group or application must be unique, as follows:</span></span>  
  
- <span data-ttu-id="e9851-104">BizTalk アセンブリと BizTalk 以外の .NET アセンブリは、どちらもその完全な名前がグループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-104">Both BizTalk assemblies and non-BizTalk .NET assemblies must have a unique full name in the group.</span></span> <span data-ttu-id="e9851-105">完全名は、ファイル名、公開キー トークン、カルチャ、およびバージョンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e9851-105">The full name consists of a file name, public key token, culture, and version.</span></span>  
  
- <span data-ttu-id="e9851-106">ルールとポリシーの名前とバージョン番号は、グループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-106">Rules and policies must have a unique name and version number in the group.</span></span>  
  
- <span data-ttu-id="e9851-107">送信ポート、送信ポート グループ、受信ポート、および受信場所の名前は、グループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-107">Send ports, send port groups, receive ports, and receive locations must have a unique name in the group.</span></span>  
  
- <span data-ttu-id="e9851-108">Web サイトの仮想ディレクトリ名はグループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-108">Web sites must have a unique virtual directory name in the group.</span></span>  
  
- <span data-ttu-id="e9851-109">BAM リソースのファイル名はグループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-109">BAM resources must have a unique file name in the group.</span></span>  
  
- <span data-ttu-id="e9851-110">証明書の拇印はグループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-110">Certificates must have a unique thumbprint in the group.</span></span>  
  
- <span data-ttu-id="e9851-111">COM コンポーネントのファイル名は、グループ内で一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e9851-111">COM components must have a unique file name in the group.</span></span>  
  
- <span data-ttu-id="e9851-112">スクリプトやその他のフラット ファイルなどのファイルベースのアイテムのファイル名は、アプリケーション内では一意でなければなりませんが、グループ内で一意である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e9851-112">File-based artifacts, such as scripts and other flat files, must have unique file names in the application, but not in the group.</span></span>  
  
  <span data-ttu-id="e9851-113">アプリケーション内で一意でなければならない種類のアイテムをアプリケーションにインポートまたは追加する場合に、そのアイテムが既にアプリケーションに存在するときは、上書きオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9851-113">You can specify the overwrite option to import or add an artifact to an application if the artifact already exists in the application and it is of a type that must be unique in an application.</span></span> <span data-ttu-id="e9851-114">グループ内で一意でなければならない種類のアイテムがグループ内の別のアプリケーションに存在する場合は、そのアイテムを追加またはインポートできません。</span><span class="sxs-lookup"><span data-stu-id="e9851-114">If the artifact already exists in another application in the group, and it is a type that must be unique in the group, you can neither add nor import it.</span></span>  
  
  <span data-ttu-id="e9851-115">グループ内のあるアプリケーションで使用する必要があるアイテムが別のアプリケーションに既に存在する場合は、そのアイテムを含んでいるアプリケーションへの参照を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e9851-115">If you need to use an artifact in one application and it already exists in another application in the group, you can create a reference to the application containing the artifact.</span></span> <span data-ttu-id="e9851-116">詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9851-116">For more information see [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9851-117">表示するほとんどの種類のアイテムの完全名、アプリケーションで、BTSTask の ListApp コマンドを使用して」の説明に従って[ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9851-117">You can view the full name of most types of artifacts in an application by using the ListApp command of BTSTask, as described in [ListApp Command](../core/listapp-command.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9851-118">参照</span><span class="sxs-lookup"><span data-stu-id="e9851-118">See Also</span></span>  
 [<span data-ttu-id="e9851-119">BizTalk アプリケーションの展開と管理について</span><span class="sxs-lookup"><span data-stu-id="e9851-119">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)