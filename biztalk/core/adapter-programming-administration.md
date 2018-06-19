---
title: アダプター プログラミングの管理 |Microsoft ドキュメント
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
ms.openlocfilehash: 7b19e3285357bb067614aae9472eb099470fe27f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229810"
---
# <a name="adapter-programming-administration"></a><span data-ttu-id="4bc6b-102">アダプター プログラミングの管理</span><span class="sxs-lookup"><span data-stu-id="4bc6b-102">Adapter Programming Administration</span></span>
<span data-ttu-id="4bc6b-103">特殊な種類の構成ストア アプリケーションは、アダプターは: つまり、アダプターは、他のシングル サインオンや構成ストア アプリケーションと名前空間を共有するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4bc6b-103">An adapter is a special type of configuration store application: that is, an adapter is a component that shares a namespace with other Single Sign-On and configuration store applications.</span></span> <span data-ttu-id="4bc6b-104">このため、ISSOConfigStore を使用するアダプターに関する情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4bc6b-104">Therefore, you can access information about an adapter using ISSOConfigStore.</span></span> <span data-ttu-id="4bc6b-105">ただし、構成ストア アプリケーションとは異なり、ISSOAdmin インターフェイスでアダプターの管理機能を実行しません。</span><span class="sxs-lookup"><span data-stu-id="4bc6b-105">But unlike a configuration store application, you do not perform administrative functions on an adapter with the ISSOAdmin interface.</span></span> <span data-ttu-id="4bc6b-106">代わりに、ISSOPSAdmin を通じてアダプターを管理します。</span><span class="sxs-lookup"><span data-stu-id="4bc6b-106">Instead, you administer an adapter through ISSOPSAdmin.</span></span> <span data-ttu-id="4bc6b-107">特殊なアダプターの管理インターフェイスが存在するのは、他のアクティビティと構成ストアをシステムが調整するためです。</span><span class="sxs-lookup"><span data-stu-id="4bc6b-107">The reason for a specialized adapter administration interface is so that the system can coordinate other activities with the configuration store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc6b-108">参照</span><span class="sxs-lookup"><span data-stu-id="4bc6b-108">See Also</span></span>  
 <span data-ttu-id="4bc6b-109">[アダプター プログラミングの構成](../core/adapter-programming-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4bc6b-109">[Adapter Programming Configuration](../core/adapter-programming-configuration.md) </span></span>  
 <span data-ttu-id="4bc6b-110">[アダプター グループとグループ アダプター](../core/adapter-groups-and-group-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="4bc6b-110">[Adapter Groups and Group Adapters](../core/adapter-groups-and-group-adapters.md) </span></span>  
 [<span data-ttu-id="4bc6b-111">パスワード同期アダプター</span><span class="sxs-lookup"><span data-stu-id="4bc6b-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)