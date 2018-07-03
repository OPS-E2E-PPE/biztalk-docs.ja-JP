---
title: プロパティ スキーマを非表示にしたりする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [schemas], showing
- schemas, properties
- managing [schemas], hiding
- managing [schemas], properties
ms.assetid: e7cc1838-cc3f-4dd3-a7d1-e66e7ee82d0c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5cc4708692e659019cf8d95a18868929f75654
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985403"
---
# <a name="how-to-show-and-hide-property-schemas"></a><span data-ttu-id="c6c3a-102">プロパティ スキーマを表示または非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="c6c3a-102">How to Show and Hide Property Schemas</span></span>
<span data-ttu-id="c6c3a-103">このトピックでは、BizTalk Server 管理コンソールを使用してアプリケーションの Schemas フォルダーでプロパティ スキーマを表示または非表示にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-103">This topic describes how to use the BizTalk Server Administration console to show and hide property schemas in the Schemas folder for an application.</span></span> <span data-ttu-id="c6c3a-104">プロパティ スキーマは、昇格させたプロパティを、インスタンス メッセージからメッセージ コンテキストへ、あるいは、メッセージ コンテキストからインスタンス メッセージへとコピーするプロセスを実行する、簡易版の BizTalk スキーマといえます。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-104">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span> <span data-ttu-id="c6c3a-105">プロパティ スキーマを非表示にすると、ドキュメント スキーマのみが表示され、スキーマ ビューが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-105">You might want to hide property schemas to simplify the schema view, so that you only see document schemas.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c6c3a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c6c3a-106">Prerequisites</span></span>  
 <span data-ttu-id="c6c3a-107">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="c6c3a-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-show-or-hide-property-schemas-in-the-schemas-folder"></a><span data-ttu-id="c6c3a-109">Schemas フォルダーでプロパティ スキーマを表示または非表示にするには</span><span class="sxs-lookup"><span data-stu-id="c6c3a-109">To show or hide property schemas in the Schemas folder</span></span>  
  
1. <span data-ttu-id="c6c3a-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c6c3a-111">コンソール ツリーで、展開**BizTalk Server 管理**またはプロパティのスキーマを非表示にする schemas フォルダーが含まれる BizTalk グループ、schemas フォルダーが含まれるアプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schemas folder in which you want to show or hide property schemas, and then expand the application containing the schemas folder.</span></span>  
  
3. <span data-ttu-id="c6c3a-112">右クリックし、**スキーマ**フォルダー、いずれかをクリックします**プロパティ スキーマの非表示**または**プロパティ スキーマの**します。</span><span class="sxs-lookup"><span data-stu-id="c6c3a-112">Right-click the **Schemas** folder, and click either **Hide Property Schemas** or **Show Property Schemas**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c3a-113">参照</span><span class="sxs-lookup"><span data-stu-id="c6c3a-113">See Also</span></span>  
 [<span data-ttu-id="c6c3a-114">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="c6c3a-114">Managing Schemas</span></span>](../core/managing-schemas.md)