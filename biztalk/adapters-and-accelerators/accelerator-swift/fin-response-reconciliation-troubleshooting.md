---
title: FIN Response Reconciliation のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fa60b9b9f3034e795c191cc6a40e7288f195ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377805"
---
# <a name="fin-response-reconciliation-troubleshooting"></a>FIN Response Reconciliation のトラブルシューティング
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a>FRR BAM ビューは、メッセージのメッセージの種類を表示しません。  
  
### <a name="symptom"></a>現象  
 MRSR サイト FRR BAM ビューには、1 つまたは複数のメッセージのメッセージの種類は表示されません。 メッセージまたはメッセージの他のすべてのデータが表示され、メッセージの種類がに対して表示されるその他のすべてのメッセージ型のインスタンス。  
  
### <a name="possible-cause"></a>考えられる原因  
 FRRMessageOut アクティビティでは、F21 メッセージ (Ack/NAKs) のメッセージの種類は記録されません。  
  
### <a name="solution"></a>ソリューション  
 この問題が発生した場合は、MRSR サイト F21 メッセージとして FRR BAM ビューで表示されているメッセージの種類がないすべてのメッセージを解釈します。  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a>プロジェクトでシステム レベルのスキーマを展開するには、エラーが生成されます。  
  
### <a name="symptom"></a>現象  
 プロジェクトで FrrSchemas.dll でシステム レベルのスキーマを展開しようとしたときにエラーが表示されます。 これらのスキーマの一覧は、次を参照してください。 [FIN 応答の種類](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)します。  
  
### <a name="possible-cause"></a>考えられる原因  
 FrrSchemas.dll でシステム レベルのスキーマは、FrrSchemas.dll に既に展開されています。 再度展開エラーが発生しようとしています。  
  
### <a name="solution"></a>ソリューション  
 FrrSchemas.dll でシステム レベルのスキーマを展開する必要はありません。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)