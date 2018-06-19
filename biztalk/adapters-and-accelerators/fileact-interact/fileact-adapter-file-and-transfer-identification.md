---
title: FileAct アダプター ファイルと転送 Id |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a9aaff1-8816-42cf-b100-fedf964caaf5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5340f9ad739009ff1cb1257365ceeeb7459511a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223154"
---
# <a name="fileact-adapter-file-and-transfer-identification"></a>FileAct アダプター ファイルおよび転送の識別
A4SWIFT FileAct アダプターにより、開発者は実行時にファイル サービスおよび転送の識別の詳細を指定できます。 これらのパラメーターを以下に示します。  
  
-   **物理ファイル名**– 完全なパスと読み取りまたは書き込みするファイルの名前。 このパラメーターが渡されないと、ファイル ハンドラー コンポーネントのローカルです。  
  
-   **論理ファイル名**– SWIFTNet 間で、受信アプリケーションへの送信元アプリケーションからファイル名が渡されます。 これは省略可能であり、パスを除いた物理ファイル名が使用されます指定されていない場合。  
  
-   **ファイル転送イベント エンドポイント**– サブスクライブ イベント プリミティブでファイル転送イベント処理アプリケーションに指定した名前です。 このパラメーターは、ファイルの転送をイベントのレポートを受信するアプリケーションにリンクします。  
  
-   **ファイル転送参照**– トークン文字列が作成され、転送のハンドルとして FileAct サブシステムによって使用自体です。 これは、限り FileAct アダプターは、単なる文字列この譲渡に固有です。  
  
-   **キーを転送**– の転送を識別する、アプリケーションによって割り当てられた文字列は、目的を中止します。 指定しない場合、アプリケーションで、これは、ファイルに関連付けられている GUID です。  
  
-   **パーティションを転送**– 複数の転送を関連付けるために使用する文字列。 指定しない場合、呼び出しで、開発者が、この関連の送信を定義するときに指定された「アプリケーション名」またはされる受信場所。  
  
-   **ユーザーの参照**– 否認不可の転送を一意に識別する、アプリケーションで定義されている文字列。 指定しない場合、アプリケーションで、ファイルに関連付けられている GUID になります。  
  
-   **メッセージ ID** – 最初の要求または応答を一意に定義の識別子。 これは、送信アダプターによって生成されるたびに、適切な要求または応答メッセージに関連付けられた GUID です。 したがって、クライアントが要求のメッセージ ID を生成し、サーバーがその応答します。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプター状態の監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)