---
title: "スキーマのスキーマ定義 (XSD) を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, viewing
- managing [schemas], viewing
- viewing, schema definitions
- schemas, schema definition (XSD)
- managing [schemas], schema definition (XSD)
ms.assetid: 21b6d9e6-5737-4334-9fe6-15ae01f90c0d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941951398ec966dea0045283e13c4581f60016aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-schema-definition-xsd-of-a-schema"></a><span data-ttu-id="af7ac-102">スキーマのスキーマ定義 (XSD) を表示する方法</span><span class="sxs-lookup"><span data-stu-id="af7ac-102">How to View the Schema Definition (XSD) of a Schema</span></span>
<span data-ttu-id="af7ac-103">このトピックでは、BizTalk Server 管理コンソールを使用して、スキーマのスキーマ定義 (XSD) を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af7ac-103">This topic describes how to use the BizTalk Server Administration console to view the schema definition (XSD) of a schema.</span></span> <span data-ttu-id="af7ac-104">これは、スキーマ検証エラーのトラブルシューティングを行ったり、正しいスキーマが展開されていることを確認したりするために必要です。</span><span class="sxs-lookup"><span data-stu-id="af7ac-104">You might want to do this to troubleshoot schema validation errors or validate that the correct schema is deployed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="af7ac-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="af7ac-105">Prerequisites</span></span>  
 <span data-ttu-id="af7ac-106">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7ac-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="af7ac-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="af7ac-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-xsd-of-a-schema"></a><span data-ttu-id="af7ac-108">スキーマの XSD を表示するには</span><span class="sxs-lookup"><span data-stu-id="af7ac-108">To view the XSD of a schema</span></span>  
  
1.  <span data-ttu-id="af7ac-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="af7ac-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="af7ac-110">コンソール ツリーで  **BizTalk Server 管理コンソール**XSD を表示するスキーマが含まれる BizTalk グループを展開し、スキーマを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="af7ac-110">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to view the XSD, and then expand the application containing the schema.</span></span>  
  
3.  <span data-ttu-id="af7ac-111">をクリックして**スキーマ**、スキーマを右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="af7ac-111">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="af7ac-112">左側のウィンドウでをクリックして**スキーマ ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="af7ac-112">In the left pane, click **Schema View**.</span></span>  
  
     <span data-ttu-id="af7ac-113">右ペインに XSD が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af7ac-113">The XSD displays in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7ac-114">参照</span><span class="sxs-lookup"><span data-stu-id="af7ac-114">See Also</span></span>  
 [<span data-ttu-id="af7ac-115">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="af7ac-115">Managing Schemas</span></span>](../core/managing-schemas.md)