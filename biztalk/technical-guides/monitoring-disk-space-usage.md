---
title: ディスク領域使用率の監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ae87de0b00e70ae03a30dd8ef20ede4a972388d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298594"
---
# <a name="monitoring-disk-space-usage"></a>ディスク領域使用率の監視
運用の準備の監視プロセスの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のように使用されるディスク領域を監視します。  
  
-   **ディスクの判断に必要な領域。**  
  
     File または MSMQ を使用して、送信/受信場所、ときにの障害に対応できる十分なディスク領域があることを確認してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または受信側システムです。 たとえば場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SAN の共有への書き込みファイルは、受信側システム ダウン 2 日間、ファイルをキューに登録できるようにするには、十分なディスク領域があるかどうかを判断します。  
  
-   **BizTalk Server のバックアップ ファイルのディレクトリを定期的にクリーンアップします。**  
  
     SQL Server エージェント ジョブから呼び出されるスクリプトを使用してこのクリーンアップを行うことができます。  
  
-   **BizTalk 追跡データベースのアーカイブ ファイル ディレクトリを定期的にクリーンアップします。**  
  
-   **ピーク時のデータ フローの時間帯に大規模な BizTalk Server データベース (.mdf) とトランザクション ログ (.ldf) ファイルに対応する十分なディスク領域があることを確認します。**