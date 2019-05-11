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
# <a name="known-issues-with-the-pop3-adapter"></a>POP3 アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a>POP3 アダプターが 64 ビット オペレーティング システムで実行されているとドキュメントの処理に失敗する  
  
##### <a name="problem"></a>問題  
 POP3 アダプターが 64 ビット オペレーティング システムで実行されている場合、ドキュメントが処理されません。  
  
##### <a name="cause"></a>原因  
 POP3 アダプターのアダプター ハンドラーは、64 ビット ホストのインスタンスでは実行できません。  
  
##### <a name="resolution"></a>解決策  
 64 ビット コンピューターで POP3 アダプターを実行する場合は、POP3 アダプター ハンドラーを 32 ビット ホストで実行するように構成します。 このオプションは、BizTalk 管理コンソールの [ホストのプロパティ] ページで設定できます。  
  
## <a name="see-also"></a>参照  
 [POP3 アダプターのトラブルシューティング](../core/troubleshooting-the-pop3-adapter.md)