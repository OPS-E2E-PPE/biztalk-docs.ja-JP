---
title: 作成して、アダプター グループを変更する方法 |Microsoft Docs
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
ms.openlocfilehash: ff60beb673515421054863799f7445304a5be200
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339497"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a><span data-ttu-id="89348-102">作成して、アダプター グループを変更する方法</span><span class="sxs-lookup"><span data-stu-id="89348-102">How to Create and Modify an Adapter Group</span></span>
<span data-ttu-id="89348-103">新しい機能のシングル サインオン (SSO) の 1 つ作成し、アダプター グループを変更する機能があります。</span><span class="sxs-lookup"><span data-stu-id="89348-103">One of the new features of Single Sign-On (SSO) is the ability to create and modify adapter groups.</span></span> <span data-ttu-id="89348-104">名前が示すように、アダプターのコレクションは、アダプター グループです。</span><span class="sxs-lookup"><span data-stu-id="89348-104">As the name implies, an adapter group is a collection of adapters.</span></span> <span data-ttu-id="89348-105">アダプター グループを使用して、アダプターのセキュリティ設定およびその他のプロパティを整理することができます。</span><span class="sxs-lookup"><span data-stu-id="89348-105">You can use adapter groups to organize security settings and other properties for your adapters.</span></span>  
  
### <a name="to-create-and-modify-an-adapter-group"></a><span data-ttu-id="89348-106">作成し、アダプター グループを変更するには</span><span class="sxs-lookup"><span data-stu-id="89348-106">To create and modify an adapter group</span></span>  
  
1.  <span data-ttu-id="89348-107">Ssops ツールへの呼び出しを使用して、アダプター グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="89348-107">Create the adapter group by using a call to the ssops tool.</span></span>  
  
     <span data-ttu-id="89348-108">関連付けられている XML ファイルをアダプター グループとしてグループ フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89348-108">In the associated XML file, you must set the group flag as an adapter group.</span></span>  
  
2.  <span data-ttu-id="89348-109">使用して 1 つまたは複数のアダプターをアダプター グループに追加`ISSOPSAdmin.AddAdapterToAdapterGroup`します。</span><span class="sxs-lookup"><span data-stu-id="89348-109">Add one or more adapters to the adapter group by using `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span></span>  
  
     <span data-ttu-id="89348-110">この時点では、アダプター グループが予定どおりに機能する準備ができます。</span><span class="sxs-lookup"><span data-stu-id="89348-110">At this point, your adapter group is ready to work as intended.</span></span> <span data-ttu-id="89348-111">かどうか、必要に応じて表示する関連付けられているアダプターの完全な一覧を使用して`ISSOPSAdmin.GetAdaptersForAdapterGroup`します。</span><span class="sxs-lookup"><span data-stu-id="89348-111">If necessary, you can view the full list of associated adapters by using `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span></span>  
  
3.  <span data-ttu-id="89348-112">使用してアダプター グループの設定を変更できます`ISSOPSAdmin.SetAdapterProperties`します。</span><span class="sxs-lookup"><span data-stu-id="89348-112">You can modify the settings of your adapter group using `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
4.  <span data-ttu-id="89348-113">アダプター グループを使用して、アダプターを削除することができますが完了したら、`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`します。</span><span class="sxs-lookup"><span data-stu-id="89348-113">When you are finished, you can remove the adapter from the adapter group using `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span></span>  
  
5.  <span data-ttu-id="89348-114">使用して、アダプター グループを削除する最後に、`ISSOAdmin.DeleteApplication`します。</span><span class="sxs-lookup"><span data-stu-id="89348-114">Finally, you can delete the adapter group by using `ISSOAdmin.DeleteApplication`.</span></span>  
  
     <span data-ttu-id="89348-115">使用して、アダプター グループを削除する代わりに選択することがあります、 `-delete` ssops ツールのコマンド。</span><span class="sxs-lookup"><span data-stu-id="89348-115">You may choose instead to delete the adapter group by using the `-delete` command of the ssops tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89348-116">参照</span><span class="sxs-lookup"><span data-stu-id="89348-116">See Also</span></span>  
 [<span data-ttu-id="89348-117">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="89348-117">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)