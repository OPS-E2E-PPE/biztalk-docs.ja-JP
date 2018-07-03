---
title: スキーマ Validation2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8648b1fc098fc303f3afa2fc47733103f30a6f0a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999472"
---
# <a name="schema-validation"></a>スキーマの検証
EDI 受信パイプラインと EDI 送信パイプラインは、次のスキーマを使用してメッセージを検証します。  
  
- **エンベロープの検証**: サービス スキーマ`Microsoft.BizTalk.Edi.BaseArtifacts.dll`で [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]  
  
- **トランザクション セットの検証**: スキーマのメッセージ スキーマに格納[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]xsd_schema \edi にあります  
  
- **受信確認メッセージの検証**: CONTRL、997、および TA1 のスキーマ`Microsoft.BizTalk.Edi.BaseArtifacts.dll`します。  
  
  `Microsoft.BizTalk.Edi.BaseArtifacts.dll` 内のスキーマは、セットアップ プログラムによって自動的に展開されます。 これらのスキーマが記載されて、**スキーマ**のノード、 **BizTalk EDI アプリケーション**で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
  メッセージ スキーマを使用するには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダー内の MicrosoftEdiXSDTemplates.exe 自己解凍ファイルを実行してサーバーのハード ドライブにスキーマをインストールし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でそのスキーマをプロジェクトに展開します。  
  
  **スキーマの決定**  
  
  EDI 受信パイプラインは、受信メッセージの処理時に、アグリーメントの参照とスキーマ検索プロセスを実行して、メッセージの処理に使用するスキーマの名前空間を決定します。 詳細については、次を参照してください。[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。  
  
  EDI 送信パイプラインは、送信メッセージの作成時に、アグリーメント プロパティを使用してエンベロープに必要事項を記載した後、トランザクション セット内の情報に対してスキーマの検証を実行します。 スキーマが読み込まれると、送信パイプラインは、スキーマをアグリーメント プロパティ (アグリーメントが指定されていない場合はフォールバック アグリーメント) に照らし合わせて検証します。 スキーマの検証に成功したら、パイプラインは、そのスキーマに照らし合わせてトランザクション セットを検証します。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)