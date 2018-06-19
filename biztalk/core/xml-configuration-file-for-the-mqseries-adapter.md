---
title: MQSeries アダプターの構成ファイルを XML |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, mqsconfigwiz
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], mqsconfigwiz
- mqsconfigwiz [MQSeries adapters]
ms.assetid: 5f19e55c-0f2c-46d7-bb5d-1eb147c296b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0356c69b90f0dcfd5fc636b302a97b2de5674b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289770"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a><span data-ttu-id="d32c9-102">MQSeries アダプターの XML 構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d32c9-102">XML Configuration File for the MQSeries Adapter</span></span>
<span data-ttu-id="d32c9-103">XML 構成ファイルを読む**mqsconfigwiz** Windows 版のウィザードを使用する場合、ユーザーが入力したのと同じ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d32c9-103">The XML configuration file read by **mqsconfigwiz** contains the same information a user enters when using the Windows version of the wizard.</span></span> <span data-ttu-id="d32c9-104">たとえば、アプリケーション ID、ユーザー ID とパスワード (必要な場合)、ロール名、およびそのロールに属しているユーザーの一覧などがあります。</span><span class="sxs-lookup"><span data-stu-id="d32c9-104">This information includes the application identity and the user ID and password if required, the role name, and a list of users who are part of that role.</span></span>  
  
 <span data-ttu-id="d32c9-105">このファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d32c9-105">An example of the file might appear as follows:</span></span>  
  
```  
<MQSeriesConfig>  
    <AppIdentity>thisuser</AppIdentity>  
    <userid>domain\username</userid>  
    <password>Bippity.Boppity</password>  
    <rolename>CreatorOwner</rolename>  
    <userlist>  
        <username>domain\user1</username>  
        <username>domain\user2</username>  
    </userlist>  
</MQSeriesConfig>  
```  
  
 <span data-ttu-id="d32c9-106">使用することができます**thisuser**、 **InteractiveUser**、 **LocalService**、または**NetworkService**の値として**AppIdentity**.</span><span class="sxs-lookup"><span data-stu-id="d32c9-106">You can use **thisuser**, **InteractiveUser**, **LocalService**, or **NetworkService** as values for **AppIdentity**.</span></span> <span data-ttu-id="d32c9-107">使用して、 **userid**と**パスワード**のみを持つ要素**thisuser**です。</span><span class="sxs-lookup"><span data-stu-id="d32c9-107">Use the **userid** and **password** elements only with **thisuser**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32c9-108">参照</span><span class="sxs-lookup"><span data-stu-id="d32c9-108">See Also</span></span>  
 [<span data-ttu-id="d32c9-109">MQSeries アダプタのサイレント構成</span><span class="sxs-lookup"><span data-stu-id="d32c9-109">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)