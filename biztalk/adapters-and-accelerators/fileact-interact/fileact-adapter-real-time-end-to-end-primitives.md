---
title: FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0532c0240be0032a46100e46d9cd58d4ff4820e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367177"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a>FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ
SWIFTNet プリミティブは、アプリケーションと SWIFTNet リンク (SNL) 間で交換する XML ドキュメントのペアです。 各エンド ツー エンド プリミティブ型、そこの側をプリミティブ – クライアント (または送信) の横にあるいずれかと、サーバーで 1 つの 2 つのバージョン (または受信)。 これには、4 つのメッセージの合計が構成されています。各ファイルのプリミティブ型、ファイルの取得のプリミティブ型、および配信通知の送信を配置します。  
  
 FileAct エンド ツー エンド プリミティブの図は、次のとおりです。  
  
 ![FileAct エンド&#45;に&#45;プリミティブを終了](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")  
  
## <a name="put-file"></a>ファイルを配置します。  
 アプリケーションは、別の SWIFTNet ユーザーのファイル システムにファイルを送信するファイルの配置プリミティブを開始します。 エンド ツー エンド関数では、クライアント側とサーバーの両方の側ファイルの配置のプリミティブがあります。 これらが協調して、ファイル転送を正常に完了します。  
  
 このような各コラボレーションでは、1 つのファイルを送信します。 複数ファイルの配置のプリミティブは、並列で実行する可能性があります。  
  
## <a name="get-file"></a>ファイルを取得します。  
 アプリケーションは、別の SWIFTNet ユーザーのファイル システムからファイルを取得するファイルの取得のプリミティブを開始します。 エンド ツー エンド関数では、クライアント側とサーバー側の両方のファイルの取得のプリミティブがあります。 これらが協調して、ファイル転送を正常に完了します。  
  
 このような各コラボレーションでは、1 つのファイルを取得します。 複数のファイルの取得プリミティブは、並列で実行する可能性があります。  
  
## <a name="send-delivery-notification"></a>配信通知を送信します。  
 配置のすべてのファイルとプリミティブのすべての Get ファイルを受信側は、ファイル転送に関連する配信通知を返すファイル要求の送信側のオプションがあります。 ファイルの配置のプリミティブでは、要求メッセージには配信通知の要求が含まれます。  
  
 取得プリミティブ、ファイルの場合は、応答メッセージには、配信通知の要求が含まれています。  
  
 どちらの場合 (たとえば、バック オフィス システムの場合) に格納されている (使用することにより、転送が完了状態になったことを確認する状態のプリミティブのいずれか) 全体、ファイルが受信されたことと、ファイルを十分に安全にされたことを確認した後で、受信側アプリケーションでは、配信通知プリミティブを送信者に配信の肯定的な確認を返すとは別に実行します。 エンド ツー エンド関数では、クライアント側とサーバー側の両方の配信通知プリミティブがあります。 これらが協調して、ファイルの配信通知を正常に完了します。  
  
 配信通知には、サービスのデザイナーを構築し、送信側とファイルの受信側でプロトコルを適用する必要があります。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)