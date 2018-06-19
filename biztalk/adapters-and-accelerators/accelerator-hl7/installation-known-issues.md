---
title: 既知の問題のインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2f80ff9-b37c-49f8-8250-fcf3cec4c0fc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4e9197d2b3c448b4fd9cc42c0cdeb929917061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204546"
---
# <a name="installation-known-issues"></a><span data-ttu-id="aea50-102">インストールの既知の問題</span><span class="sxs-lookup"><span data-stu-id="aea50-102">Installation known issues</span></span>
<span data-ttu-id="aea50-103">役立つ有用な情報は、インストールの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="aea50-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="aea50-104">BTAHL7 をインストールするための前提条件</span><span class="sxs-lookup"><span data-stu-id="aea50-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="aea50-105">インストールの前提条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aea50-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
-   <span data-ttu-id="aea50-106">基本コンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン (SSO)、グループ、およびランタイムを含め、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea50-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
-   <span data-ttu-id="aea50-107">インストールして、BTAHL7 を構成するユーザーは、BizTalk 管理者グループのメンバーであり、BTAHL7 データが格納されている SQL Server の Administrators グループのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea50-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="aea50-108">SQL Server 混在モードがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="aea50-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="aea50-109">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]混在モードで SQL Server をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aea50-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="aea50-110">修復はアンインストールと変更からは機能しません</span><span class="sxs-lookup"><span data-stu-id="aea50-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="aea50-111">ユーザー アクセス制御 (UAC) が有効になっているし、コントロール パネルを使用して、インストールを修復しようとする、修復は失敗します。</span><span class="sxs-lookup"><span data-stu-id="aea50-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="aea50-112">Microsoft では、UAC が有効にしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aea50-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="aea50-113">**解決策**</span><span class="sxs-lookup"><span data-stu-id="aea50-113">**Resolution**</span></span>  
  
 <span data-ttu-id="aea50-114">実行、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]クリックし、setup.exe**修復**です。</span><span class="sxs-lookup"><span data-stu-id="aea50-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea50-115">参照</span><span class="sxs-lookup"><span data-stu-id="aea50-115">See Also</span></span>  
[<span data-ttu-id="aea50-116">インストールまたは Microsoft BizTalk Accelerator 用 HL7 にアップグレード</span><span class="sxs-lookup"><span data-stu-id="aea50-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)