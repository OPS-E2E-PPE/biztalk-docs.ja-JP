---
title: 経由でメッセージの受信場所と InfoPath フォームを送信する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4589649be79ce369f0e6756ae7f96615d4a36c0f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005123"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>経由して送信メッセージの受信場所と InfoPath フォーム
受信場所への発信メッセージを受信する[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーションです。 定義することが指定されたトランスポート プロトコルを使用してメッセージを受信するように構成する物理エンドポイントとしての受信場所。 たとえば、ファイル トランスポートを使用して、特定のファイル システム フォルダーにドロップされた受信ファイルを受信場所を構成する可能性があります。  
  
 作成する受信場所を論理的にグループ化し、管理する受信ポートの受信場所。 各受信場所に対しては、その特定の受信場所で受信したメッセージの実際の処理 (デコード、逆アセンブル、検証、およびなど) を受信パイプラインを指定します。 A4SWIFT のバインドの受信場所を受信する受信場所を論理的にグループ化し、管理するポート。  
  
 受信場所を介して A4SWIFT アプリケーションに SWIFT メッセージを送信するに、メッセージ、構成されている受信場所にドロップした、SWIFT の逆アセンブラーを使用して、受信パイプラインによって処理されるを解析し、SWIFT 逆アセンブラーによって検証し、メッセージ ボックス データベースに公開します。 メッセージがメッセージ ボックス データベースへ発行されると、A4SWIFT アプリケーションの他のコンポーネントは、追加の処理 (サブスクリプションを使用して) メッセージを取得します。 たとえば、最終的なルーティングの送信ポートを使用することができます。  
  
 作成と構成の詳細については受信ポートと受信場所、BizTalk Server ヘルプを参照してください。  
  
 経由で新しいメッセージを送信することも、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、Message Repair and New Submission の機能を使用します。 これを行うには、開く、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォルダーからそのメッセージの形式です。 内のデータを入力する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、証明書を使用して署名し、して送信します。 Message Repair and New Submission のオーケストレーションは、メッセージを処理します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT ランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)