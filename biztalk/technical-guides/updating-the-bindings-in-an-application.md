---
title: アプリケーションのバインドの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0add0638196e992f74ab53ebda7c429c97ca3aab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996563"
---
# <a name="updating-the-bindings-in-an-application"></a><span data-ttu-id="751e8-102">アプリケーションのバインドを更新しています</span><span class="sxs-lookup"><span data-stu-id="751e8-102">Updating the Bindings in an Application</span></span>
<span data-ttu-id="751e8-103">アプリケーションのアセンブリを更新すると、多くの場合、そのバインドが上書きされます。また、アセンブリがまったくバインドされず、バインドの再構成を手動で行う必要が生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="751e8-103">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="751e8-104">これを回避するには、バインド ファイルを使用してアセンブリの同じバージョンを更新または新しいバージョンでアセンブリを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="751e8-104">To avoid this, you can use a binding file to update the same version of the assembly or update an assembly with a newer version.</span></span>  
  
## <a name="updating-the-same-version-of-an-assembly"></a><span data-ttu-id="751e8-105">アセンブリの同じバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="751e8-105">Updating the Same Version of an Assembly</span></span>  
 <span data-ttu-id="751e8-106">アセンブリに事前バインドされたポートまたは動的ポートがあり、ポート構成を BizTalk Server 管理コンソールで変更した場合、このアセンブリを同じバージョン番号のアセンブリで更新すると、設定は失われます。</span><span class="sxs-lookup"><span data-stu-id="751e8-106">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="751e8-107">更新しようとするアセンブリのバインド ファイルをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="751e8-107">You can export a binding file for the assembly that you are going to update.</span></span> <span data-ttu-id="751e8-108">アセンブリを更新した後、アプリケーションにアセンブリをインポートし、以前のバインドを再適用するには、そのバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="751e8-108">After updating the assembly, you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
## <a name="updating-an-assembly-with-a-newer-version"></a><span data-ttu-id="751e8-109">新しいバージョンでアセンブリを更新しています</span><span class="sxs-lookup"><span data-stu-id="751e8-109">Updating an Assembly with a Newer Version</span></span>  
 <span data-ttu-id="751e8-110">アセンブリのバージョンを更新するには、バインディングのバインド ファイルに 1 つのアセンブリに関連付けられている、新しいアセンブリのバージョンを反映するように、バインド ファイルを編集し、アプリケーションにアセンブリのバインドをインポートおよびエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="751e8-110">You can update the version of an assembly by exporting the binding associated with a single assembly into a binding file, editing the binding file to reflect a new assembly version, and then importing the bindings of the assembly into the application.</span></span> <span data-ttu-id="751e8-111">バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=155000)(HYPERLINK"<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="751e8-111">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkID=155000) ( HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>