---
title: セキュリティと Windows インストーラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4418994a4b5ff705d1faef751ac8c96ba86f9dc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269786"
---
# <a name="security-and-windows-installer"></a><span data-ttu-id="5ddd7-102">セキュリティと Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="5ddd7-102">Security and Windows Installer</span></span>
<span data-ttu-id="5ddd7-103">Windows インストーラーは、BizTalk アプリケーションをインストールおよび更新するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-103">Windows Installer is a powerful tool for installing and updating BizTalk applications.</span></span> <span data-ttu-id="5ddd7-104">Windows インストーラーを使用する場合は、悪意を持って作成された Windows インストーラー (.msi) ファイルがもたらす可能性のあるセキュリティ上の問題に注意し、これを回避するための適切な措置をとる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-104">When using Windows Installer, you should be aware of the security issues that can be created by malicious Windows Installer (.msi) file creators and take steps to prevent them.</span></span>  
  
 <span data-ttu-id="5ddd7-105">一般に、.msi ファイルを実行するのは管理者であるため、アプリケーションのインストールまたは更新時に実行するプロセスには高度な権限が与えられています。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-105">Administrators typically run .msi files, and therefore the processes that run during application installation or update have very high privileges.</span></span> <span data-ttu-id="5ddd7-106">悪意のある .msi ファイル作成者によって、このことが次のように悪用されないとも限りません。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-106">A malicious .msi file creator could exploit this fact in a number of ways, including the following:</span></span>  
  
-   <span data-ttu-id="5ddd7-107">システムまたはファイルに望ましくない変更を加えるスクリプト ファイルを実行する。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-107">Running script files that make undesirable changes to your system or files.</span></span>  
  
-   <span data-ttu-id="5ddd7-108">COM カタログを上書きする。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-108">Overwriting the COM catalog.</span></span>  
  
-   <span data-ttu-id="5ddd7-109">レジストリ値を上書きする。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-109">Overwriting registry values.</span></span> <span data-ttu-id="5ddd7-110">このような変更はロールバックできません。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-110">These changes cannot be rolled back.</span></span>  
  
-   <span data-ttu-id="5ddd7-111">ファイル システムを飽和状態にする。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-111">Flooding the file system.</span></span>  
  
 <span data-ttu-id="5ddd7-112">.msi ファイルを使用する際は、少なくとも次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-112">When dealing with .msi files, you should take the following precautions at a minimum:</span></span>  
  
-   <span data-ttu-id="5ddd7-113">全面的に信頼できる .msi ファイルのみをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-113">Install only .msi files that you completely trust.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ddd7-114">ベスト プラクティスとして、.msi ファイルの作成担当者は、ファイルのソースが信頼できることをユーザーが確認できるように .msi ファイルに署名する追加手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-114">As a best practice, individuals who are responsible for generating .msi files should take additional steps to sign the .msi files so that users can verify that the source of the file is trusted.</span></span>  
  
-   <span data-ttu-id="5ddd7-115">.msi ファイルを実稼働環境で使用する前に十分にテストします。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-115">Thoroughly test your .msi files before using them in a production environment.</span></span>  
  
-   <span data-ttu-id="5ddd7-116">.msi ファイルは、適切な随意アクセス制御リスト (DACL) によってセキュリティで保護される保護フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="5ddd7-116">Store the .msi files in protected folders that are secured with appropriate discretionary access control lists (DACLs).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ddd7-117">参照</span><span class="sxs-lookup"><span data-stu-id="5ddd7-117">See Also</span></span>  
 [<span data-ttu-id="5ddd7-118">アプリケーションの展開のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5ddd7-118">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)