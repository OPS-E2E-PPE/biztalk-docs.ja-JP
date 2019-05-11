---
title: SSO コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7e00ad4dfb82d2c6e16c45a09c4f452b33081b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401758"
---
# <a name="sso-components"></a><span data-ttu-id="d7a90-102">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d7a90-102">SSO Components</span></span>
<span data-ttu-id="d7a90-103">エンタープライズ シングル サインオン (SSO) service のサブサービスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7a90-103">The sub services of the Enterprise Single Sign-On (SSO) service are as follows:</span></span>  
  
-   <span data-ttu-id="d7a90-104">**マッピングします。**</span><span class="sxs-lookup"><span data-stu-id="d7a90-104">**Mapping.**</span></span> <span data-ttu-id="d7a90-105">このコンポーネントは、バックエンド システムでユーザー アカウントを Windows システムでユーザー アカウントをマップします。</span><span class="sxs-lookup"><span data-stu-id="d7a90-105">This component maps the user account in the Windows system to the user accounts in the back-end systems.</span></span>  
  
-   <span data-ttu-id="d7a90-106">**参照します。**</span><span class="sxs-lookup"><span data-stu-id="d7a90-106">**Lookup.**</span></span> <span data-ttu-id="d7a90-107">このコンポーネントは、バックエンド システムでは、SSO データベース内のユーザーの資格情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="d7a90-107">This component looks up the user credentials in the SSO database in the back-end system.</span></span> <span data-ttu-id="d7a90-108">これは、SSO ランタイム コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d7a90-108">This is the SSO runtime component.</span></span>  
  
-   <span data-ttu-id="d7a90-109">**管理します。**</span><span class="sxs-lookup"><span data-stu-id="d7a90-109">**Administration.**</span></span> <span data-ttu-id="d7a90-110">このコンポーネントは、関連アプリケーションと関連アプリケーションごとのマッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="d7a90-110">This component manages the affiliate applications and the mappings for each affiliate application.</span></span>  
  
-   <span data-ttu-id="d7a90-111">**シークレット。**</span><span class="sxs-lookup"><span data-stu-id="d7a90-111">**Secret.**</span></span> <span data-ttu-id="d7a90-112">このコンポーネントは、マスター シークレットを生成し、システム内の他の SSO サーバーに配布します。</span><span class="sxs-lookup"><span data-stu-id="d7a90-112">This component generates the master secret and distributes it to the other SSO servers in the system.</span></span> <span data-ttu-id="d7a90-113">マスター シークレット サーバーとして動作しているシングル サインオン サーバーでアクティブなだけです。</span><span class="sxs-lookup"><span data-stu-id="d7a90-113">It is only active on the Single Sign-On server that is acting as the master secret server.</span></span>  
  
-   <span data-ttu-id="d7a90-114">**パスワード同期します。**</span><span class="sxs-lookup"><span data-stu-id="d7a90-114">**Password Synchronization.**</span></span> <span data-ttu-id="d7a90-115">このコンポーネントは、SSO データベースの管理を簡略化し、ユーザー ディレクトリ間でパスワード同期を保ちます。</span><span class="sxs-lookup"><span data-stu-id="d7a90-115">This component simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a90-116">参照</span><span class="sxs-lookup"><span data-stu-id="d7a90-116">See Also</span></span>  
 <span data-ttu-id="d7a90-117">[SSO サーバー](../core/sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7a90-117">[SSO Server](../core/sso-server.md) </span></span>  
 [<span data-ttu-id="d7a90-118">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="d7a90-118">Installing SSO</span></span>](../core/installing-sso.md)