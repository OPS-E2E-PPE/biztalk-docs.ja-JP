---
title: FileAct アダプターのセキュリティ アーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5faeebd6-5287-4ac4-a1db-e3c055d323d2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed8352b788af12fd3c38f489e9ddb65d8375f2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222794"
---
# <a name="fileact-adapter-security-architecture"></a>FileAct アダプターのセキュリティ アーキテクチャ
ファイル送信および受信確認のセキュリティは、SNL と、SAG に固有の証明書と暗号化の機能を使用して実装されます。  証明書などの管理は完全に FileAct アダプターの範囲外です。 関連付けられた SNL/SAG インスタンスがサービスに登録された、FileAct SWIFT および SNL/SAG に正しくインストールされているソフトウェアと、限り、アダプターは施設を介して SNL Api です。 FileAct アダプターでは、"Advanced"(ベスト プラクティス) に FACryptoMode は常に設定します。  
  
> [!NOTE]
>  アダプターの場合は、送信ポートごとに個別のセキュリティ コンテキストを作成できます。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプター状態の監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)