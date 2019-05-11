---
title: インストールされている Web サービスを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 096e21d2d7449e27f407bf7b286174c9ecb9cc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340805"
---
# <a name="how-to-configure-the-installed-web-service"></a><span data-ttu-id="fd158-102">インストールされている Web サービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fd158-102">How to Configure the Installed Web Service</span></span>
<span data-ttu-id="fd158-103">Web サービス ファイルをインストールした後は、Web サービスからメッセージを受信する BizTalk Server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd158-103">After you install the Web service files, you must configure BizTalk Server to receive messages from the Web service.</span></span>  
  
### <a name="to-configure-the-web-service"></a><span data-ttu-id="fd158-104">Web サービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="fd158-104">To configure the Web service</span></span>  
  
1.  <span data-ttu-id="fd158-105">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、Web サービスを構成するアプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fd158-105">In BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then right-click the application that you want to configure the Web Service.</span></span>  
  
2.  <span data-ttu-id="fd158-106">をポイント**インポート**、 をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="fd158-106">Point to **Import**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="fd158-107">配布フォルダに BindingInfo.xml ファイルを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fd158-107">Select the BindingInfo.xml file in the distribution folder, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="fd158-108">オーケストレーションを起動し、受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd158-108">Start your orchestrations and enable receive locations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd158-109">参照</span><span class="sxs-lookup"><span data-stu-id="fd158-109">See Also</span></span>  
 <span data-ttu-id="fd158-110">[BizTalk アプリケーションにバインドをインポートする方法](../core/how-to-import-bindings-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="fd158-110">[How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="fd158-111">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="fd158-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)