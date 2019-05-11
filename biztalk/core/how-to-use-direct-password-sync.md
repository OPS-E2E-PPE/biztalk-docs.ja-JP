---
title: 直接パスワード同期を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9baa74b383ee30c1fba70c7f9bb966706d60142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333542"
---
# <a name="how-to-use-direct-password-sync"></a><span data-ttu-id="0260d-102">直接パスワード同期を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0260d-102">How to Use Direct Password Sync</span></span>
<span data-ttu-id="0260d-103">エンタープライズ シングル サインオンのこのバージョンには、Windows の機能から直接パスワード同期が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0260d-103">This version of Enterprise Single Sign-On includes the Direct Password Sync from Windows feature.</span></span> <span data-ttu-id="0260d-104">これにより、パスワード同期アダプターをバイパスし、Windows から直接、SSO データベースのパスワードを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="0260d-104">This enables you to bypass a Password Sync Adapter and update the password in the SSO Database directly from Windows.</span></span>  
  
 <span data-ttu-id="0260d-105">Windows から直接パスワード同期では、次の状況で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0260d-105">Direct Password Sync from Windows is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="0260d-106">エンタープライズ システムでは、Windows のマッピングに Windows が必要です。</span><span class="sxs-lookup"><span data-stu-id="0260d-106">Your enterprise system requires Windows to Windows mapping.</span></span>  
  
-   <span data-ttu-id="0260d-107">Windows ユーザーのパスワードの変更が発生したときに、SSO データベースで外部ユーザーのパスワードを直接更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0260d-107">You need to update the External User’s password in the SSO database directly when a password change occurs for the Windows user.</span></span> <span data-ttu-id="0260d-108">その他のメカニズムを使用して (つまり、外部ユーザーに対応します)、バック エンド システムのパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0260d-108">You can change the password on the back-end system (that corresponds to the external user) by using other mechanisms.</span></span> <span data-ttu-id="0260d-109">たとえば、Microsoft Identity Integration Server を使用して、リソースへのアクセス管理機能 (RACF) RACF 管理エージェントを使用して、IBM メインフレームでパスワードを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="0260d-109">For example, you can use Microsoft Identity Integration Server to update passwords in Resource Access Control Facility (RACF) on an IBM Mainframe using the RACF Management Agent.</span></span>  
  
### <a name="to-enable-direct-password-sync"></a><span data-ttu-id="0260d-110">直接パスワード同期を有効にするには</span><span class="sxs-lookup"><span data-stu-id="0260d-110">To enable Direct Password Sync</span></span>  
  
1.  <span data-ttu-id="0260d-111">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="0260d-111">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="0260d-112">スコープ ペインで次のようにクリックします。**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="0260d-112">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="0260d-113">適切な右**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="0260d-113">Right-click the appropriate **Affiliate Application**.</span></span>  
  
4.  <span data-ttu-id="0260d-114">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0260d-114">Click **Properties**.</span></span>  
  
     <span data-ttu-id="0260d-115">**関連アプリケーションのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0260d-115">The **Affiliate Applications Properties** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="0260d-116">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="0260d-116">Click the **Options** tab.</span></span>  
  
6.  <span data-ttu-id="0260d-117">選択、 **Windows から直接パスワード同期**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="0260d-117">Select the **Direct Password Sync from Windows** check box.</span></span>  
  
7.  <span data-ttu-id="0260d-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0260d-118">Click **OK**.</span></span>