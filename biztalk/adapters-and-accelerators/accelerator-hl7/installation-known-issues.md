---
title: インストールの既知の問題 |Microsoft Docs
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
ms.openlocfilehash: 3c95a8de4437f2ae52c01f77fbfe6e4ff0d559d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300077"
---
# <a name="installation-known-issues"></a><span data-ttu-id="27c0e-102">インストールの既知の問題</span><span class="sxs-lookup"><span data-stu-id="27c0e-102">Installation known issues</span></span>
<span data-ttu-id="27c0e-103">役立つ有用な情報は、インストールの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="27c0e-103">Useful information that may help you avoid installation problems.</span></span>  
  
## <a name="prerequisites-for-installing-btahl7"></a><span data-ttu-id="27c0e-104">BTAHL7 のインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="27c0e-104">Prerequisites for installing BTAHL7</span></span>  
 <span data-ttu-id="27c0e-105">インストールの前提条件[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]次に示します。</span><span class="sxs-lookup"><span data-stu-id="27c0e-105">The prerequisites for installing [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] include the following:</span></span>  
  
- <span data-ttu-id="27c0e-106">基本コンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン (SSO)、グループ、およびランタイムを含む、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c0e-106">Basic components of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], including Enterprise Single Sign-On (SSO), Group, and Runtime, should be configured.</span></span>  
  
- <span data-ttu-id="27c0e-107">インストールと構成 BTAHL7 のユーザーは、BizTalk 管理者グループのメンバーと BTAHL7 データが格納されている SQL Server の Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c0e-107">The user installing and configuring BTAHL7 must be a member of the BizTalk Administrators group, and a member of the Administrators group on the SQL Server where the BTAHL7 data is stored.</span></span>
  
## <a name="sql-server-mixed-mode-not-supported"></a><span data-ttu-id="27c0e-108">SQL Server 混在モードがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="27c0e-108">SQL Server mixed mode not supported</span></span>  
<span data-ttu-id="27c0e-109">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]混在モードで SQL Server をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="27c0e-109">The [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] does not support SQL Server in mixed mode.</span></span>  
  
## <a name="repair-does-not-work-from-uninstallchange"></a><span data-ttu-id="27c0e-110">修復はアンインストールと変更からは機能しません</span><span class="sxs-lookup"><span data-stu-id="27c0e-110">Repair does not work from uninstall/change</span></span>  
<span data-ttu-id="27c0e-111">ユーザー アクセス制御 (UAC) が有効になっているし、コントロール パネルを使用して、インストールを修復しようとする、修復は失敗します。</span><span class="sxs-lookup"><span data-stu-id="27c0e-111">If user access control (UAC) is enabled, and you try to repair your installation using the control panel, the repair fails.</span></span> 

<span data-ttu-id="27c0e-112">Microsoft では、UAC を有効にしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27c0e-112">Microsoft recommends you keep UAC enabled.</span></span>

 <span data-ttu-id="27c0e-113">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="27c0e-113">**Resolution**</span></span>  
  
 <span data-ttu-id="27c0e-114">実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe、および選択**修復**します。</span><span class="sxs-lookup"><span data-stu-id="27c0e-114">Run the [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] setup.exe, and then select **Repair**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c0e-115">参照</span><span class="sxs-lookup"><span data-stu-id="27c0e-115">See Also</span></span>  
[<span data-ttu-id="27c0e-116">Microsoft BizTalk Accelerator for HL7 のインストールまたはアップグレード</span><span class="sxs-lookup"><span data-stu-id="27c0e-116">Install or upgrade Microsoft BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)