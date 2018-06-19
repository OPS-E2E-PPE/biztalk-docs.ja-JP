---
title: インストールされている Web サービスを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, configuring
- deploying, Web services
- Web services, deploying
ms.assetid: 5a281daa-9e1c-47b0-9002-66ea18ed6caf
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54d5fd99bfa9f5a7440202848c4d43259d0a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247778"
---
# <a name="how-to-configure-the-installed-web-service"></a><span data-ttu-id="941e8-102">インストールされている Web サービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="941e8-102">How to Configure the Installed Web Service</span></span>
<span data-ttu-id="941e8-103">Web サービス ファイルをインストールした後、その Web サービスからメッセージを受信するように BizTalk Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="941e8-103">After you install the Web service files, you must configure BizTalk Server to receive messages from the Web service.</span></span>  
  
### <a name="to-configure-the-web-service"></a><span data-ttu-id="941e8-104">Web サービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="941e8-104">To configure the Web service</span></span>  
  
1.  <span data-ttu-id="941e8-105">BizTalk Server 管理コンソールで、 **BizTalk グループ**、展開**アプリケーション**、Web サービスを構成する場合、アプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="941e8-105">In BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then right-click the application that you want to configure the Web Service.</span></span>  
  
2.  <span data-ttu-id="941e8-106">をポイント**インポート**、クリックして**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="941e8-106">Point to **Import**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="941e8-107">配布フォルダに BindingInfo.xml ファイルを選択し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="941e8-107">Select the BindingInfo.xml file in the distribution folder, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="941e8-108">オーケストレーションを開始し、受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="941e8-108">Start your orchestrations and enable receive locations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941e8-109">参照</span><span class="sxs-lookup"><span data-stu-id="941e8-109">See Also</span></span>  
 <span data-ttu-id="941e8-110">[BizTalk アプリケーションにバインドをインポートする方法](../core/how-to-import-bindings-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="941e8-110">[How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="941e8-111">非 Visual Studio コンピューターに公開された Web サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="941e8-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)