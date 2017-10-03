---
title: "FIN 対応調整のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a92812086f191d5777b387d9861b32a3147c1e96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-troubleshooting"></a>FIN 対応調整のトラブルシューティング
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a>FRR BAM ビューは、メッセージのメッセージの種類を表示しません。  
  
### <a name="symptom"></a>現象  
 MRSR サイト FRR BAM ビューには、1 つまたは複数のメッセージのメッセージの種類は表示されません。 メッセージまたはメッセージの他のすべてのデータが表示され、に対してメッセージの種類が表示されるその他のすべてのメッセージ型のインスタンス。  
  
### <a name="possible-cause"></a>考えられる原因  
 FRRMessageOut アクティビティでは、F21 メッセージ (Ack/NAKs) のメッセージの種類は記録しません。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合は、F21 メッセージとして MRSR サイト FRR BAM ビューに表示されているメッセージ型を持たないすべてのメッセージを解釈します。  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a>プロジェクト内のシステム レベルのスキーマを展開するには、エラーが生成されます。  
  
### <a name="symptom"></a>現象  
 プロジェクトで FrrSchemas.dll でシステム レベルのスキーマを展開しようとしたときにエラーが発生します。 これらのスキーマの一覧は、次を参照してください。 [FIN 応答タイプ](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)です。  
  
### <a name="possible-cause"></a>考えられる原因  
 FrrSchemas.dll でシステム レベルのスキーマが FrrSchemas.dll に展開します。 展開しようにもう一度、エラーが発生します。  
  
### <a name="solution"></a>解決方法  
 FrrSchemas.dll でシステム レベルのスキーマを展開する必要はありません。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)