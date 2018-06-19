---
title: 作成し、アダプター グループを変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249226"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a><span data-ttu-id="2bd99-102">作成し、アダプター グループを変更する方法</span><span class="sxs-lookup"><span data-stu-id="2bd99-102">How to Create and Modify an Adapter Group</span></span>
<span data-ttu-id="2bd99-103">シングル サインオン (SSO) に新たに実装された機能の 1 つに、アダプター グループを作成したり変更したりする機能があります。</span><span class="sxs-lookup"><span data-stu-id="2bd99-103">One of the new features of Single Sign-On (SSO) is the ability to create and modify adapter groups.</span></span> <span data-ttu-id="2bd99-104">アダプター グループとは、その名前からわかるように、複数のアダプターを 1 つにまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="2bd99-104">As the name implies, an adapter group is a collection of adapters.</span></span> <span data-ttu-id="2bd99-105">アダプター グループを使用することで、一連のアダプターのプロパティ (セキュリティ設定など) を体系的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-105">You can use adapter groups to organize security settings and other properties for your adapters.</span></span>  
  
### <a name="to-create-and-modify-an-adapter-group"></a><span data-ttu-id="2bd99-106">アダプター グループを作成および変更するには</span><span class="sxs-lookup"><span data-stu-id="2bd99-106">To create and modify an adapter group</span></span>  
  
1.  <span data-ttu-id="2bd99-107">ssops ツールの呼び出しを使用して、アダプター グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bd99-107">Create the adapter group by using a call to the ssops tool.</span></span>  
  
     <span data-ttu-id="2bd99-108">関連する XML ファイルで、グループ フラグをアダプター グループとして設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bd99-108">In the associated XML file, you must set the group flag as an adapter group.</span></span>  
  
2.  <span data-ttu-id="2bd99-109">`ISSOPSAdmin.AddAdapterToAdapterGroup` を使用して、アダプター グループに 1 つまたは複数のアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="2bd99-109">Add one or more adapters to the adapter group by using `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span></span>  
  
     <span data-ttu-id="2bd99-110">これでアダプター グループを使用する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="2bd99-110">At this point, your adapter group is ready to work as intended.</span></span> <span data-ttu-id="2bd99-111">必要であれば、`ISSOPSAdmin.GetAdaptersForAdapterGroup` を使用して、関連付けられたアダプターを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-111">If necessary, you can view the full list of associated adapters by using `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span></span>  
  
3.  <span data-ttu-id="2bd99-112">`ISSOPSAdmin.SetAdapterProperties` を使用して、アダプター グループの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-112">You can modify the settings of your adapter group using `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
4.  <span data-ttu-id="2bd99-113">以上の作業を終えた後は、`ISSOPSAdmin.RemoveAdapterFromAdapterGroup` を使用して、アダプター グループからアダプターを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-113">When you are finished, you can remove the adapter from the adapter group using `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span></span>  
  
5.  <span data-ttu-id="2bd99-114">最後に、`ISSOAdmin.DeleteApplication` を使用して、アダプター グループを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-114">Finally, you can delete the adapter group by using `ISSOAdmin.DeleteApplication`.</span></span>  
  
     <span data-ttu-id="2bd99-115">ssops ツールの `-delete` コマンドを使用してアダプター グループを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bd99-115">You may choose instead to delete the adapter group by using the `-delete` command of the ssops tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd99-116">参照</span><span class="sxs-lookup"><span data-stu-id="2bd99-116">See Also</span></span>  
 [<span data-ttu-id="2bd99-117">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="2bd99-117">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)