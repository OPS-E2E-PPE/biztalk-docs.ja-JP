---
title: 直接パスワード同期を使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255946"
---
# <a name="how-to-use-direct-password-sync"></a><span data-ttu-id="1f000-102">直接パスワード同期を使用する方法</span><span class="sxs-lookup"><span data-stu-id="1f000-102">How to Use Direct Password Sync</span></span>
<span data-ttu-id="1f000-103">このバージョンのエンタープライズ シングル サインオンには、Windows から実行できる直接パスワード同期機能が実装されています。</span><span class="sxs-lookup"><span data-stu-id="1f000-103">This version of Enterprise Single Sign-On includes the Direct Password Sync from Windows feature.</span></span> <span data-ttu-id="1f000-104">この機能により、パスワード同期アダプタをバイパスし、SSO データベースのパスワードの更新を Windows から直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="1f000-104">This enables you to bypass a Password Sync Adapter and update the password in the SSO Database directly from Windows.</span></span>  
  
 <span data-ttu-id="1f000-105">Windows からの直接パスワード同期は、次のような場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f000-105">Direct Password Sync from Windows is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="1f000-106">エンタープライズ システムで Windows から Windows へのマッピングが必要な場合。</span><span class="sxs-lookup"><span data-stu-id="1f000-106">Your enterprise system requires Windows to Windows mapping.</span></span>  
  
-   <span data-ttu-id="1f000-107">Windows ユーザーのパスワードに変更が生じた場合は、SSO データベースにある外部ユーザーのパスワードを直接更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f000-107">You need to update the External User’s password in the SSO database directly when a password change occurs for the Windows user.</span></span> <span data-ttu-id="1f000-108">パスワードの変更は、他のメカニズムを使用することにより、(外部ユーザーに対応する) バックエンド システム上で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f000-108">You can change the password on the back-end system (that corresponds to the external user) by using other mechanisms.</span></span> <span data-ttu-id="1f000-109">たとえば、RACF 管理エージェントを使用した IBM メインフレーム上の Resource Access Control Facility (RACF) にあるパスワードを、Microsoft Identity Integration Server を使用して更新することが可能です。</span><span class="sxs-lookup"><span data-stu-id="1f000-109">For example, you can use Microsoft Identity Integration Server to update passwords in Resource Access Control Facility (RACF) on an IBM Mainframe using the RACF Management Agent.</span></span>  
  
### <a name="to-enable-direct-password-sync"></a><span data-ttu-id="1f000-110">直接パスワード同期を有効にするには</span><span class="sxs-lookup"><span data-stu-id="1f000-110">To enable Direct Password Sync</span></span>  
  
1.  <span data-ttu-id="1f000-111">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f000-111">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="1f000-112">スコープ ペインで、をクリックして**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="1f000-112">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="1f000-113">適切なを右クリックして**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="1f000-113">Right-click the appropriate **Affiliate Application**.</span></span>  
  
4.  <span data-ttu-id="1f000-114">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f000-114">Click **Properties**.</span></span>  
  
     <span data-ttu-id="1f000-115">**関連アプリケーションのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f000-115">The **Affiliate Applications Properties** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="1f000-116">クリックして、**オプション**タブです。</span><span class="sxs-lookup"><span data-stu-id="1f000-116">Click the **Options** tab.</span></span>  
  
6.  <span data-ttu-id="1f000-117">選択、 **Windows から直接パスワード同期**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1f000-117">Select the **Direct Password Sync from Windows** check box.</span></span>  
  
7.  <span data-ttu-id="1f000-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f000-118">Click **OK**.</span></span>