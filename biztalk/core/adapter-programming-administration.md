---
title: アダプター プログラミングの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c81d056e9775ec0e9273f01aa11be384f632647
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361349"
---
# <a name="adapter-programming-administration"></a><span data-ttu-id="195f0-102">アダプター プログラミングの管理</span><span class="sxs-lookup"><span data-stu-id="195f0-102">Adapter Programming Administration</span></span>
<span data-ttu-id="195f0-103">アダプターが特別な種類の構成ストア アプリケーション。 これは、アダプターは、その他のシングル サインオンおよび構成ストア アプリケーションと、名前空間を共有するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="195f0-103">An adapter is a special type of configuration store application: that is, an adapter is a component that shares a namespace with other Single Sign-On and configuration store applications.</span></span> <span data-ttu-id="195f0-104">そのため、ISSOConfigStore を使用して、アダプターについての情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="195f0-104">Therefore, you can access information about an adapter using ISSOConfigStore.</span></span> <span data-ttu-id="195f0-105">構成ストア アプリケーションとは異なりを実行しない管理機能、ISSOAdmin インターフェイスでアダプター。</span><span class="sxs-lookup"><span data-stu-id="195f0-105">But unlike a configuration store application, you do not perform administrative functions on an adapter with the ISSOAdmin interface.</span></span> <span data-ttu-id="195f0-106">代わりに、ISSOPSAdmin を通じてアダプターを管理します。</span><span class="sxs-lookup"><span data-stu-id="195f0-106">Instead, you administer an adapter through ISSOPSAdmin.</span></span> <span data-ttu-id="195f0-107">特殊化されたアダプターの管理インターフェイスの理由が設定されて、システムは、構成ストアとその他のアクティビティを調整できます。</span><span class="sxs-lookup"><span data-stu-id="195f0-107">The reason for a specialized adapter administration interface is so that the system can coordinate other activities with the configuration store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195f0-108">参照</span><span class="sxs-lookup"><span data-stu-id="195f0-108">See Also</span></span>  
 <span data-ttu-id="195f0-109">[アダプター プログラミングの構成](../core/adapter-programming-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="195f0-109">[Adapter Programming Configuration](../core/adapter-programming-configuration.md) </span></span>  
 <span data-ttu-id="195f0-110">[アダプター グループとグループ アダプター](../core/adapter-groups-and-group-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="195f0-110">[Adapter Groups and Group Adapters](../core/adapter-groups-and-group-adapters.md) </span></span>  
 [<span data-ttu-id="195f0-111">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="195f0-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)