---
title: DBNETLIB 例外の回避 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc51bd9e997e4cca8526f855495b1ceec9f7e81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358717"
---
# <a name="avoiding-dbnetlib-exceptions"></a>DBNETLIB 例外の回避
BizTalk Server ランタイムがメッセージ ボックス データベースまたは管理データベースのいずれかと通信できない場合、DBNetLib (データベース ネットワーク ライブラリ) エラーが発生します。 このエラーが発生すると、例外をキャッチする BizTalk Server ランタイム インスタンスがシャットダウンし、データベースが使用可能かどうかの確認が 1 分ごとに反復されます。  
  
 DBNetLib エラーの最も一般的な原因は、(多数あると考えられる) メッセージ ボックス データベース サーバーの 1 つが極端なビジー状態になったときに、そのサーバーへの通信がなおも試みられ、DBNetLib 例外の原因となるタイムアウトが発生することです。  
  
 メッセージ ボックス データベースが単にビジー状態になる以外にも、メッセージ ボックス データベースをホストする BizTalk データベース サーバーが I/O (入力/出力) バインドであるときに、実稼働環境で DBNetLib エラーが発生する可能性があります。  
  
 ここでは、DBNetLib エラーが誘発される条件と、それらのエラーを回避するための推奨事項について説明します。  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a>DBNetLib エラーの原因と解決方法  
  
### <a name="symptoms-of-a-dbnetlib-error"></a>DBNetLib エラーの現象  
 Microsoft BizTalk Server ホスト インスタンスが終了して自動的に再起動し、BizTalk Server アプリケーション ログに、以下のようなエラーが書き込まれます。  
  
```  
Event Type:Warning  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:5410  
Computer:BIZTALKSERVER  
Description:  
An error occurred that requires the BizTalk service to terminate. The most common causes are the following:  
 1) An unexpected out of memory error.  
 OR  
 2) An inability to connect or a loss of connectivity to one of the BizTalk databases.   
 The service will shutdown and auto-restart in 1 minute. If the problematic database remains unavailable, this cycle will repeat.  
  
 Error message: [DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation.  
 Error source:    
  
 BizTalk host name: BizTalkHost  
 Windows service name: BTSSvc$BizTalkHost   
  
---------------------------------------------------------  
Event Type:Error  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:6913  
Computer:BIZTALKSERVER  
Description:  
An attempt to connect to "BizTalkMsgBoxDb" SQL Server database on server "SQLSERVER " failed.  
 Error: "[DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation."  
```  
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a>メッセージ ボックス データベースをホストする BizTalk データベース サーバーが I/O バインドになる  
 BizTalk サーバーは、メッセージ ボックス データベースをホストするデータベース サーバーと直接通信し、機能します。 メッセージ ボックス データベースをホストするデータベース サーバーは、使用率が高くなり I/O (入力/出力) バインドの状態になると、応答を返さなくなる場合があります。 その結果、BizTalk サーバーの 1 つが、応答しないデータベース サーバーの 1 つとの接続を失って、DBNetLib エラーが発生します。  
  
 マイクロソフトでのテストによると、使用率が高いデータベース サーバーの物理ディスクの "% Idle Time" が低下し続け、10% を下回ると I/O バインドになることがわかっています。 "% Idle Time" がこのレベルを下回るまで低下し続けている場合、データベース サーバーが応答しない状態に近づいていることを示しています。  
  
#### <a name="cause"></a>原因  
 メッセージ ボックス データベースをホストするデータベース サーバーが I/O バインドになる原因はいくつかあります。次に、その一部を示します。  
  
-   メッセージ ボックス データベースをホストするデータベース コンピューターが、メモリ容量やプロセッサの数が少ない、プロセッサが低速など、仕様の低いハードウェアの制約を受けている場合。  
  
-   メッセージ ボックス データベースをホストするデータベース コンピューターの物理ディスクを、使用率が高い他のデータベースと共有している場合。 (メッセージ ボックスを含む) 複数のデータベースの使用率が同時に高くなると、物理ディスクが I/O バインドになる場合があります。  
  
     以下に、このような状況の例を示します。  
  
     マイクロソフトでのテストによると、BizTalkDTADb データベースか BAM データベース、またはその両方をホストするデータベース サーバーで、物理ディスクの % Disk Read Time と % Disk Write Time が高いパーセンテージを示す場合があることがわかっています。 メッセージ ボックス データベースをホストするデータベース サーバーのディスクを、BizTalkDTADb、BAM など、使用率が高い他のデータベースと共有しているとき、2 つのデータベースの使用率が同時に高くなった場合、データベース サーバーの物理ディスクが I/O バインドになり、応答を返さなくなる場合があります。  
  
-   BizTalkDTADb と 1 つ以上のメッセージ ボックス データベースがデータベース サーバーの同一の物理ディスクを共有している場合は、アーカイブと削除を頻繁に実行しないと、ディスクが I/O バインドになる場合があります。  
  
#### <a name="resolution"></a>解決策  
 BizTalk メッセージ ボックスをホストするデータベース サーバーが、使用率が高まって応答を返さなくなる状況を回避します。  
  
 次に、サーバーのディスクの使用率が高まる主な原因の一部を、問題緩和の推奨事項と共に示します。  
  
##### <a name="low-hardware-specs"></a>低いハードウェア仕様  
 マイクロソフトでのテストによると、処理しようとしている負荷がハードウェアの仕様を上回るときに、サーバーの使用率が高まることがわかっています。 ハードウェア仕様が低いと、データベースで発生するアクティビティの量によっては、システムにすぐに負荷がかかります。 その結果、サーバーの % Disk Read Time と % Disk Write Time が安定せずに増加し続け、ディスクの % Idle Time が 10% を下回るまで減少し続けて、データベース サーバーが応答しなくなる場合があります。  
  
 高負荷時にデータベース サーバーが応答しなくなることが判明した場合、BizTalk 展開のアクティビティの量と負荷に応じて、CPU やメモリの増設、SAN への接続などで、データベース サーバーをアップグレードすることを検討してください。 また、ハードウェアのうち、アップグレードを必要とするボトルネックが、(メモリ、CPU の数など) どの部分かを調査するため、適切な診断を行ってください。  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a>複数の BizTalk データベース グループによる 1 つのサーバーまたは 1 枚のディスクの共有  
 既に説明したとおり、BizTalk 追跡 (BizTalkDTADb) データベース、BAM データベースなど、メッセージ ボックス以外のデータベースは、サーバーの物理ディスクのサイクルを多く消費する場合があります。 つまり、これらのデータベースがメッセージ ボックス データベースと同一の物理ディスクを共有する場合、ディスクが停止し、応答しなくなることがあるので、結果的に BizTalk サーバーがメッセージ ボックス データベースへの接続を失い、DBNetLib が発生します。  
  
 サーバーの物理ディスクの使用率を上昇させることが予測されるデータベースは、BizTalk メッセージ ボックスから切り離し、別の物理ディスクに分ける (または、別のサーバーに分ける) ことを強くお勧めします。 BizTalkDTADb データベースおよび BAM データベースを、メッセージ ボックスとは別の独自のドライブやサーバーに配置すること、およびメッセージ ボックス データベースが複数ある場合は、1 つずつ独自のディスクに配置することをお勧めします。  
  
##### <a name="archiving-and-purging"></a>アーカイブと削除  
 BizTalkDTADb データベースとメッセージ ボックス データベースが同一サーバーの同一ディスクを共有している場合、BizTalkDTADb データベースは、アーカイブと削除を定期的に行わない限り、無制限にサイズが増加します。  
  
 テストの結果、アーカイブと削除を定期的に行うことが推奨されますが、通常よりも高い負荷がかかる場合は、アーカイブと削除の実行頻度を増やすことを検討してください。 BizTalkDTADb データベース サイズの増加を定期的にメンテナンスしないと、最終的にアーカイブと削除を実行したときに時間が非常にかかるうえ、実行中はデータベース サーバーの使用可能なリソースのほとんどが消費される可能性があります。