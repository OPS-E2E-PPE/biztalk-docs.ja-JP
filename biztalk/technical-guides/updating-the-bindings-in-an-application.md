---
title: "アプリケーションのバインドの更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4d30296a2bb81b3685793884010f02eb950828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="updating-the-bindings-in-an-application"></a><span data-ttu-id="27c5d-102">アプリケーションのバインドを更新</span><span class="sxs-lookup"><span data-stu-id="27c5d-102">Updating the Bindings in an Application</span></span>
<span data-ttu-id="27c5d-103">アプリケーションのアセンブリを更新すると、多くの場合、そのバインドが上書きされます。また、アセンブリがまったくバインドされず、バインドの再構成を手動で行う必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-103">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="27c5d-104">これを回避するのには、同じバージョンのアセンブリを更新または新しいバージョンでアセンブリを更新するバインド ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-104">To avoid this, you can use a binding file to update the same version of the assembly or update an assembly with a newer version.</span></span>  
  
## <a name="updating-the-same-version-of-an-assembly"></a><span data-ttu-id="27c5d-105">アセンブリの同じバージョンの更新</span><span class="sxs-lookup"><span data-stu-id="27c5d-105">Updating the Same Version of an Assembly</span></span>  
 <span data-ttu-id="27c5d-106">アセンブリに事前バインドされたポートまたは動的ポートがあり、ポート構成を BizTalk Server 管理コンソールで変更した場合、このアセンブリを同じバージョン番号のアセンブリで更新すると、設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-106">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="27c5d-107">更新しようとするアセンブリのバインド ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-107">You can export a binding file for the assembly that you are going to update.</span></span> <span data-ttu-id="27c5d-108">アセンブリを更新した後、アプリケーションにアセンブリをインポートし、以前のバインドを再適用するには、そのバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-108">After updating the assembly, you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
## <a name="updating-an-assembly-with-a-newer-version"></a><span data-ttu-id="27c5d-109">アセンブリを新しいバージョンと更新</span><span class="sxs-lookup"><span data-stu-id="27c5d-109">Updating an Assembly with a Newer Version</span></span>  
 <span data-ttu-id="27c5d-110">アセンブリのバージョンを更新するには、バインド ファイルに 1 つのアセンブリに関連付けられているバインディング、アセンブリの新しいバージョンを反映するように、バインド ファイルを編集し、アプリケーションにアセンブリのバインドのインポートおよびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="27c5d-110">You can update the version of an assembly by exporting the binding associated with a single assembly into a binding file, editing the binding file to reflect a new assembly version, and then importing the bindings of the assembly into the application.</span></span> <span data-ttu-id="27c5d-111">バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=155000)(ハイパーリンク"http://go.microsoft.com/fwlink/?LinkID=155000"http://go.microsoft.com/fwlink/?LinkID=155000) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="27c5d-111">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkID=155000) ( HYPERLINK "http://go.microsoft.com/fwlink/?LinkID=155000" http://go.microsoft.com/fwlink/?LinkID=155000) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>