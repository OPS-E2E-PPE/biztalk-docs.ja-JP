---
title: アダプター プログラミングの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: e908b3ac79970b917e1e7964868b3b9d5bd852d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229986"
---
# <a name="adapter-programming-configuration"></a><span data-ttu-id="a91eb-102">アダプター プログラミングの構成</span><span class="sxs-lookup"><span data-stu-id="a91eb-102">Adapter Programming Configuration</span></span>
<span data-ttu-id="a91eb-103">パスワード同期アダプターは、その設計対象となるシステムによって構成の要件が異なります。</span><span class="sxs-lookup"><span data-stu-id="a91eb-103">Every type of password sync adapter has different configuration requirements, depending on what non-Windows system you design the adapter for.</span></span> <span data-ttu-id="a91eb-104">関連アプリケーションと同様、エンタープライズ シングル サインオンの構成ストアを使用することにより、構成プロパティを集中的かつより安全に保存できます。</span><span class="sxs-lookup"><span data-stu-id="a91eb-104">Like affiliate applications, you can use the Enterprise Single Sign-On configuration store to store configuration properties centrally and more securely.</span></span>  
  
 <span data-ttu-id="a91eb-105">管理者は、他の構成ストア アプリケーションと同じように、エンタープライズ シングル サインオンの管理ユーザー インターフェイスを使って、アダプターの構成プロパティが指定されている XML ファイルを検索し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a91eb-105">As with other configuration store applications, an administrator can use the Enterprise Single Sign-On management user interface to locate and read an XML file that describes the configuration properties for your adapter.</span></span> <span data-ttu-id="a91eb-106">管理ツールは、プロパティ ページをレンダリングする際、XML ファイルを使って、指定されたアダプターで必要となるプロパティ値を収集します。</span><span class="sxs-lookup"><span data-stu-id="a91eb-106">The management tools use the XML file to render a property page to gather the required property values, for the specified adapter.</span></span> <span data-ttu-id="a91eb-107">また、XML に格納されたプロパティ (名前/値ペア) は、ISSOConfigStore や SSOPS ツールを使用して構成ストアに保存したり、構成ストアから読み込んだりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a91eb-107">You can also use ISSOConfigStore to load and read XML name/value combinations to and from the configuration store, or you can use the SSOPS tool.</span></span>  
  
 <span data-ttu-id="a91eb-108">エンタープライズ シングル サインオンの管理ツールを使用して、アダプターの有効と無効を切り替えることも可能です。</span><span class="sxs-lookup"><span data-stu-id="a91eb-108">You can also use the Enterprise Single Sign-On administration tools to enable and disable an adapter.</span></span> <span data-ttu-id="a91eb-109">構成を最初に作成するとき、アダプターは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a91eb-109">On initial creation, an adapter is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a91eb-110">参照</span><span class="sxs-lookup"><span data-stu-id="a91eb-110">See Also</span></span>  
 [<span data-ttu-id="a91eb-111">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="a91eb-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)