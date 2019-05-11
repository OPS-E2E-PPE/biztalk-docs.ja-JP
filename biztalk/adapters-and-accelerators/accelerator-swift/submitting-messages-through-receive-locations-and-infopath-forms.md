---
title: 経由でメッセージの受信場所と InfoPath フォームの送信 |Microsoft Docs
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
ms.openlocfilehash: ebf95acf08084f7382e166efdace182a4464178c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377011"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>経由して送信メッセージの受信場所と InfoPath フォーム
受信場所に送信するメッセージを受信する[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション。 定義することが指定されたトランスポート プロトコルを使用してメッセージを受信するように構成する物理エンドポイントとしての受信場所。 たとえば、受信場所は、ファイル トランスポートを使用して、特定のファイル システム フォルダーにドロップされた受信ファイルを構成できます。  
  
 作成する受信場所を論理的にグループ化し、管理する受信ポートの受信場所。 各受信場所の受信パイプラインで、その特定の受信場所で受信したメッセージの実際の処理 (デコード、逆アセンブル、検証、およびなど) を指定します。 A4SWIFT のバインドを受信する場所を受信する受信場所を論理的にグループ化して管理されるポート。  
  
 A4SWIFT 受信場所を使用してアプリケーションに SWIFT メッセージを送信するメッセージ構成されている受信場所にドロップ、SWIFT 逆アセンブラーを使用して受信パイプラインによって処理されるを解析し、SWIFT 逆アセンブラーによって検証し、メッセージ ボックス データベースに発行されます。 メッセージがメッセージ ボックス データベースにパブリッシュされた後、A4SWIFT アプリケーションでは、その他のコンポーネントは、追加の処理 (サブスクリプションを使用して) メッセージを取得します。 たとえば、最終的なルーティングの送信ポートを使用することができます。  
  
 作成と構成の詳細については受信ポートと受信場所、BizTalk Server のヘルプを参照してください。  
  
 新しいメッセージを送信することもできます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームの Message Repair and New Submission の機能を使用します。 これを行うには、開く、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォルダーからそのメッセージの形式。 データを格納する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、証明書を使用してサインインし、それを送信します。 Message Repair and New Submission のオーケストレーションは、メッセージを処理します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT ランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)