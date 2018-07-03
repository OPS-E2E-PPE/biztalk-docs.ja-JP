---
title: ディスク領域の使用状況の監視 |Microsoft Docs
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
ms.openlocfilehash: 25035d50c6e69fcf74e1cf75e8f073b19cc0b47f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986931"
---
# <a name="monitoring-disk-space-usage"></a>ディスク領域の使用状況の監視
運用準備状況の監視プロセスの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のように使用されるディスク領域を監視します。  

- **ディスクの決定に必要な領域。**  

   送信/受信場所を使用して File または MSMQ を使用しているときの障害に対応するために使用可能な十分なディスク領域があることを確認します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または受信側システム。 たとえば場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]キューにファイルを許可するには、十分なディスク領域があるかどうか、SAN の共有への書き込みファイルは、受信側のシステムが 2 日間がダウンします。  

- **BizTalk Server のバックアップ ファイルのディレクトリを定期的にクリーンアップします。**  

   SQL Server エージェント ジョブから呼び出されるスクリプトを使用してこのクリーンアップを行うことができます。  

- **BizTalk 追跡データベースのアーカイブ ファイル ディレクトリを定期的にクリーンアップします。**  

- **大規模な BizTalk Server データベース (.mdf) とトランザクション ログ (.ldf) ファイルをデータ フローのピーク時間帯に対応するために十分なディスク領域があることを確認します。**
