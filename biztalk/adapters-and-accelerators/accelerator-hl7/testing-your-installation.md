---
title: インストールのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d2d94ffce01bd299ad836b7f1fb7c82f66a8196
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971907"
---
# <a name="testing-your-installation"></a>インストールのテスト
設定することができます、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のエンド ツー エンド チュートリアルを手動で実行されているか、エンド ツー エンド チュートリアル プログラムを実行することによってテスト用インストールします。 プログラムを実行するをクリックするか、 **Launch Tutorial**セットアップ中にボタンまたは C:\Program files \microsoft biztalk EndToEndTutorial.exe を実行\<バージョン\>HL7\SDK\ のアクセラレータ(後のインストールと構成を実行している) エンド ツー エンド チュートリアル フォルダーです。 これらの自動化されたアクションのいずれかは、チュートリアルを実行して手動で実行する同じセットアップ手順を実行します。 エンド ツー エンド チュートリアル プログラムは、次を行います。  
  
- MSH と確認のスキーマをデプロイします。  
  
- Version 2.3.1 の一般的なスキーマをデプロイします。  
  
- ADT スキーマをデプロイします。  
  
- 作成、Tutorial_1WayReceive 受信ポート  
  
- 作成、Tutorial_MLLPReceive 受信場所  
  
- 作成、Tutorial_BTAHL7PickUp 受信ポート  
  
- 作成、Tutorial_FileReceiveLoc 受信場所  
  
- Tutorial_sendAck_ADT 送信ポートを作成します。  
  
- Tutorial_sendMsg_RX 送信ポートを作成します。  
  
- Tutorial_BTAHL7Drop 送信ポートを作成します。  
  
- Tutorial_MLLPSend 送信ポートを作成します。  
  
- Tutorial_ADTSystem パーティを作成します。  
  
- Tutorial_RXSystem パーティを作成します。  
  
- Tutorial_HISystem パーティを作成します。  
  
- BizTalk サービスを再起動します。  
  
  エンド ツー エンド チュートリアル プログラムを実行した場合は、HL7 定義済みフォルダーでのテスト インスタンスを削除できます。 フォルダーに関連付けられている受信パイプラインはメッセージを取得し、それを処理します。 フィルターに基づき、送信パイプラインは、目的のフォルダーにドキュメントをルーティングします。 Microsoft の基本的な構成要素を実行する単純な「ラウンド トリップ」がこの[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンジンし、インストールを確認します。  
  
### <a name="to-test-your-installation"></a>インストールをテストします。  
  
1. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7\SDK\End ツー エンド チュートリアル フォルダー。  
  
2. 右クリックし、 **TutorialSampleInstance.txt**ファイルを開き、をクリックし、**コピー**します。  
  
3. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7PickUp フォルダーです。  
  
4. フォルダーを右クリックし、**貼り付け**します。  
  
5. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7Drop フォルダーです。  
  
    かどうか、インストールが正常に処理済みのインスタンスが表示される場合を確認することができます、 **Tutorial_BTAHL7Drop**フォルダーとして\< *Guid*\>.txt します。  
  
   次の手順に進む[チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)します。