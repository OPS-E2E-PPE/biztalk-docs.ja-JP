---
title: FileAct アダプターのセキュリティ アーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: be9997dca0a4b7a5c619848e4ed38cf9099bbc16
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826378"
---
# <a name="fileact-adapter-security-architecture"></a>FileAct アダプターのセキュリティ アーキテクチャ
SNL と、SAG に固有の証明書と暗号化機能を使用して、ファイルの送信と受信確認のセキュリティが実装されます。  証明書などの管理は完全に FileAct アダプターの範囲外です。 SWIFT に FileAct のサービスの関連付けられた SNL/SAG インスタンスが登録されているし、SNL/SAG、アダプターに正しくインストールされているソフトウェアは、長い SNL api 機能を使用します。 FileAct アダプターでは、"Advanced"(ベスト プラクティス) に FACryptoMode は常に設定します。  
  
> [!NOTE]
>  アダプターの場合は、各送信ポートの別のセキュリティ コンテキストを作成できます。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
