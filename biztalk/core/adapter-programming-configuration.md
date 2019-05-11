---
title: アダプター プログラミングの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b407c6f0239798110b7b971ffa4febd58d6f70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361341"
---
# <a name="adapter-programming-configuration"></a><span data-ttu-id="b27ee-102">アダプター プログラミングの構成</span><span class="sxs-lookup"><span data-stu-id="b27ee-102">Adapter Programming Configuration</span></span>
<span data-ttu-id="b27ee-103">パスワード同期アダプターのすべての種類には、用のアダプターをデザインするどのような非 Windows システムに応じて、別の構成要件があります。</span><span class="sxs-lookup"><span data-stu-id="b27ee-103">Every type of password sync adapter has different configuration requirements, depending on what non-Windows system you design the adapter for.</span></span> <span data-ttu-id="b27ee-104">関連アプリケーションと同様、一元的より安全に、構成プロパティを格納するのにエンタープライズ シングル サインオンの構成ストアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b27ee-104">Like affiliate applications, you can use the Enterprise Single Sign-On configuration store to store configuration properties centrally and more securely.</span></span>  
  
 <span data-ttu-id="b27ee-105">その他の構成ストアのアプリケーションを管理者は、検索し、アダプターの構成プロパティを記述する XML ファイルの読み取りをエンタープライズ シングル サインオンの管理のユーザー インターフェイスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b27ee-105">As with other configuration store applications, an administrator can use the Enterprise Single Sign-On management user interface to locate and read an XML file that describes the configuration properties for your adapter.</span></span> <span data-ttu-id="b27ee-106">管理ツールは、指定したアダプタの必要なプロパティの値を収集するためにプロパティ ページを表示するために、XML ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b27ee-106">The management tools use the XML file to render a property page to gather the required property values, for the specified adapter.</span></span> <span data-ttu-id="b27ee-107">XML 名前/値の組み合わせと、構成ストアの間の読み込みと読み取りを ISSOConfigStore を使用することもできます。 または、SSOPS ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b27ee-107">You can also use ISSOConfigStore to load and read XML name/value combinations to and from the configuration store, or you can use the SSOPS tool.</span></span>  
  
 <span data-ttu-id="b27ee-108">アダプターを無効にする、エンタープライズ シングル サインオンの管理ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b27ee-108">You can also use the Enterprise Single Sign-On administration tools to enable and disable an adapter.</span></span> <span data-ttu-id="b27ee-109">最初に作成、アダプターは無効です。</span><span class="sxs-lookup"><span data-stu-id="b27ee-109">On initial creation, an adapter is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27ee-110">参照</span><span class="sxs-lookup"><span data-stu-id="b27ee-110">See Also</span></span>  
 [<span data-ttu-id="b27ee-111">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="b27ee-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)