---
title: "SSO コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-components"></a><span data-ttu-id="9edf4-102">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9edf4-102">SSO Components</span></span>
<span data-ttu-id="9edf4-103">エンタープライズ シングル サインオン (SSO) サービスには、次のサブサービスがあります。</span><span class="sxs-lookup"><span data-stu-id="9edf4-103">The sub services of the Enterprise Single Sign-On (SSO) service are as follows:</span></span>  
  
-   <span data-ttu-id="9edf4-104">**マッピングです。**</span><span class="sxs-lookup"><span data-stu-id="9edf4-104">**Mapping.**</span></span> <span data-ttu-id="9edf4-105">Windows システムのユーザー アカウントをバックエンド システムのユーザー アカウントにマップします。</span><span class="sxs-lookup"><span data-stu-id="9edf4-105">This component maps the user account in the Windows system to the user accounts in the back-end systems.</span></span>  
  
-   <span data-ttu-id="9edf4-106">**参照です。**</span><span class="sxs-lookup"><span data-stu-id="9edf4-106">**Lookup.**</span></span> <span data-ttu-id="9edf4-107">バックエンド システムの SSO データベースに格納されているユーザーの資格情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="9edf4-107">This component looks up the user credentials in the SSO database in the back-end system.</span></span> <span data-ttu-id="9edf4-108">これは SSO ランタイム コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9edf4-108">This is the SSO runtime component.</span></span>  
  
-   <span data-ttu-id="9edf4-109">**管理します。**</span><span class="sxs-lookup"><span data-stu-id="9edf4-109">**Administration.**</span></span> <span data-ttu-id="9edf4-110">関連アプリケーションと各関連アプリケーションのマッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="9edf4-110">This component manages the affiliate applications and the mappings for each affiliate application.</span></span>  
  
-   <span data-ttu-id="9edf4-111">**シークレット。**</span><span class="sxs-lookup"><span data-stu-id="9edf4-111">**Secret.**</span></span> <span data-ttu-id="9edf4-112">マスタ シークレットを生成し、システム内の他の SSO サーバーにマスタ シークレットを配布します。</span><span class="sxs-lookup"><span data-stu-id="9edf4-112">This component generates the master secret and distributes it to the other SSO servers in the system.</span></span> <span data-ttu-id="9edf4-113">マスタ シークレットは、マスタ シークレット サーバーとして機能しているシングル サインオン サーバーでのみアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="9edf4-113">It is only active on the Single Sign-On server that is acting as the master secret server.</span></span>  
  
-   <span data-ttu-id="9edf4-114">**パスワード同期します。**</span><span class="sxs-lookup"><span data-stu-id="9edf4-114">**Password Synchronization.**</span></span> <span data-ttu-id="9edf4-115">SSO データベースの管理を簡略化し、ユーザー ディレクトリ間でパスワードを常に同期した状態で保ちます。</span><span class="sxs-lookup"><span data-stu-id="9edf4-115">This component simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9edf4-116">参照</span><span class="sxs-lookup"><span data-stu-id="9edf4-116">See Also</span></span>  
 <span data-ttu-id="9edf4-117">[SSO サーバー](../core/sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="9edf4-117">[SSO Server](../core/sso-server.md) </span></span>  
 [<span data-ttu-id="9edf4-118">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="9edf4-118">Installing SSO</span></span>](../core/installing-sso.md)