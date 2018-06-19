---
title: スキーマ Validation2 |Microsoft ドキュメント
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
ms.openlocfilehash: 317fa8e0e5e557993922bba383ebf5eca460fa69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269242"
---
# <a name="schema-validation"></a>スキーマの検証
EDI 受信パイプラインと EDI 送信パイプラインは、次のスキーマを使用してメッセージを検証します。  
  
-   **エンベロープの検証**: サービス スキーマを`Microsoft.BizTalk.Edi.BaseArtifacts.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]  
  
-   **トランザクション セットの検証**: に、スキーマ内のメッセージ スキーマを格納[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]xsd_schema \edi  
  
-   **受信確認メッセージの検証**: CONTRL、997、および TA1 のスキーマ`Microsoft.BizTalk.Edi.BaseArtifacts.dll`です。  
  
 `Microsoft.BizTalk.Edi.BaseArtifacts.dll` 内のスキーマは、セットアップ プログラムによって自動的に展開されます。 これらのスキーマは、「、**スキーマ**のノード、 **BizTalk EDI アプリケーション**で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 メッセージ スキーマを使用するには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダー内の MicrosoftEdiXSDTemplates.exe 自己解凍ファイルを実行してサーバーのハード ドライブにスキーマをインストールし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でそのスキーマをプロジェクトに展開します。  
  
 **スキーマの決定**  
  
 EDI 受信パイプラインは、受信メッセージの処理時に、アグリーメントの参照とスキーマ検索プロセスを実行して、メッセージの処理に使用するスキーマの名前空間を決定します。 詳細については、次を参照してください。[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。  
  
 EDI 送信パイプラインは、送信メッセージの作成時に、アグリーメント プロパティを使用してエンベロープに必要事項を記載した後、トランザクション セット内の情報に対してスキーマの検証を実行します。 スキーマが読み込まれると、送信パイプラインは、スキーマをアグリーメント プロパティ (アグリーメントが指定されていない場合はフォールバック アグリーメント) に照らし合わせて検証します。 スキーマの検証に成功したら、パイプラインは、そのスキーマに照らし合わせてトランザクション セットを検証します。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)