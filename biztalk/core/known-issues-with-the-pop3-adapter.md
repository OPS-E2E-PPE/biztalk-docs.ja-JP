---
title: POP3 アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78e978ed5be5fa556411566d35aa6fcf58c09fec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380740"
---
# <a name="known-issues-with-the-pop3-adapter"></a><span data-ttu-id="c59e2-102">POP3 アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="c59e2-102">Known Issues with the POP3 Adapter</span></span>
<span data-ttu-id="c59e2-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="c59e2-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c59e2-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c59e2-104">Known Issues</span></span>  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a><span data-ttu-id="c59e2-105">POP3 アダプターが 64 ビット オペレーティング システムで実行されているとドキュメントの処理に失敗する</span><span class="sxs-lookup"><span data-stu-id="c59e2-105">The POP3 Adapter fails to process documents when running on a 64 bit operating system</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="c59e2-106">問題</span><span class="sxs-lookup"><span data-stu-id="c59e2-106">Problem</span></span>  
 <span data-ttu-id="c59e2-107">POP3 アダプターが 64 ビット オペレーティング システムで実行されている場合、ドキュメントが処理されません。</span><span class="sxs-lookup"><span data-stu-id="c59e2-107">The POP3 Adapter will not process documents when running on a 64 bit operating system.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="c59e2-108">原因</span><span class="sxs-lookup"><span data-stu-id="c59e2-108">Cause</span></span>  
 <span data-ttu-id="c59e2-109">POP3 アダプターのアダプター ハンドラーは、64 ビット ホストのインスタンスでは実行できません。</span><span class="sxs-lookup"><span data-stu-id="c59e2-109">The POP3 Adapter adapter handler is unable to run in a 64 bit host instance.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="c59e2-110">解決策</span><span class="sxs-lookup"><span data-stu-id="c59e2-110">Resolution</span></span>  
 <span data-ttu-id="c59e2-111">64 ビット コンピューターで POP3 アダプターを実行する場合は、POP3 アダプター ハンドラーを 32 ビット ホストで実行するように構成します。</span><span class="sxs-lookup"><span data-stu-id="c59e2-111">If you are running the POP3 Adapter on a 64 bit machine, configure the POP3 Adapter handlers to run in a 32 bit host.</span></span> <span data-ttu-id="c59e2-112">このオプションは、BizTalk 管理コンソールの [ホストのプロパティ] ページで設定できます。</span><span class="sxs-lookup"><span data-stu-id="c59e2-112">This option is available on the Host Properties page accessible from the BizTalk Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59e2-113">参照</span><span class="sxs-lookup"><span data-stu-id="c59e2-113">See Also</span></span>  
 [<span data-ttu-id="c59e2-114">POP3 アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c59e2-114">Troubleshooting the POP3 Adapter</span></span>](../core/troubleshooting-the-pop3-adapter.md)