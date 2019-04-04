---
title: ポーリングを使用して、受信呼び出しのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae02a93a-808f-4774-a2c4-efdf39a4d49a
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 868e56730f21235e3f73f6ab91a463ea4589bafd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984667"
---
# <a name="support-for-inbound-calls-using-polling"></a>ポーリングを使用して、受信呼び出しのサポート
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]クライアント プログラムから Oracle E-business Suite の Oracle E-business Suite でのデータへの変更を知らせるメッセージを受信できるようにします。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプターが指定された SQL ステートメント、ストアド プロシージャ、関数、またはパッケージ内のプロシージャを実行する場合、「ポーリング ベース」のメッセージの受信をサポートしていますが、データを取得しの一定の間隔でクライアントに結果を提供します。時間です。  

> [!NOTE]
>  ポーリング操作でのアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 インターフェイス テーブルまたはビューのインターフェイスで、操作を実行する場合は、ポーリング操作のアプリケーション コンテキストを設定する必要があります。 アプリケーションのコンテキスト、および設定する方法については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

 使用して一般的なポーリング操作、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次が含まれます。  

1. アダプターのクライアントを指定する必要があります`Polling`の受信の操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は**ポーリング**します。  

2. アダプター クライアントの SELECT ステートメントを指定する必要があります、 **PolledDataAvailableStatement**ポーリングに使用できるデータがあるかどうかを決定するプロパティをバインドします。 このステートメントの実行時に返される設定の最初の結果の最初の行の最初の列に正の整数値が含まれている場合は日付のポーリングに使用できます。  

3. アダプター クライアントのポーリング間隔を指定する必要があります、 **PollingInterval**間隔を秒単位で指定したステートメントを定義するプロパティのバインド、 **PolledDataAvailableStatement**プロパティのバインドが実行されます。 ポーリング間隔の最後に、ポーリング済みデータの使用可能なステートメントを実行して、結果セットが返されます。  

4. SELECT ステートメントまたはストアド プロシージャのアダプターのクライアントを指定する必要があります、 **PollingInput**プロパティをバインドします。 テーブルまたはビューをポーリングする場合は、このバインドのプロパティの SELECT ステートメントを指定する必要があります。 ストアド プロシージャを使用してポーリングする場合は、このバインドのプロパティの全体の要求メッセージを指定する必要があります。  

    内のステートメント、 **PollingInput**によって決定される、ポーリングに使用できるデータが場合にのみ実行プロパティのバインド、 **PolledDataAvailableStatement**手順 2. でプロパティをバインドします。  

5. アダプターのクライアントがポーリング操作のアクションを指定する必要があります、 **PollingAction**プロパティをバインドします。 Consume Adapter Service アドインを使用して、操作の生成されたメタデータから特定の操作のポーリング アクションが決定されます。  

6. アダプターのクライアントが使用できる、 **PollWhileDataFound**ポーリング間隔を無視し、継続的に使用可能な場合と、データをポーリングするプロパティをバインドします。  

   > [!IMPORTANT]
   >  値を設定した場合、 **PollWhileDataFound**バインド プロパティを True に、アダプターのクライアントがポーリング継続的に、プロセスと Oracle からのデータがループ内での Oracle データベースへの接続を開いたり閉じたりします。 ODP.NET 接続を開く率は、閉じられている接続よりも大きいが、時間がたつと、接続が使い果たされると、例外がスローされます。 回避策としては、ことを確認しますの値、 **UseOracleConnectionPool**を True に設定されている適切な値に記載されて、 **IncrPoolSize**接続の数を制御するプロパティのバインドアダプター クライアントしてを開くことができます。  

7. アダプター クライアント用、Oracle PL/SQL ブロック、ポーリング後ステートメントを指定できます、 **PostPollStatement**プロパティをバインドします。 指定されたステートメントの後にこのバインドのプロパティで指定されたステートメントが実行、 **PollingInput**プロパティのバインドを実行します。  

   > [!NOTE]
   >  アダプターで指定されたステートメントを実行する、 **PollingInput**と**PostPollStatement**プロパティをトランザクションにバインドします。 内のトランザクションの詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター処理トランザクションはどのようにですか?](https://msdn.microsoft.com/library/dd788428.aspx)します。  

   アダプターは、Oracle E-business Suite からすべての空のポーリング応答を抑制します。  

   次の図でポーリング ワークフローに関する情報を提供する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 ポーリング ワークフローの 2 つのシナリオを示します。  

8. ときの値、 **PollWhileDataFound**が"False"(既定の設定) に設定します。  

9. ときの値、 **PollWhileDataFound** "は True"に設定されている。  

   ![ポーリングのシナリオ&#40;PollWhileDataFound&#61;False&#41;](../../adapters-and-accelerators/adapter-oracle-ebs/media/e5f00f4c-cc76-4e8b-9991-b4471f9d4865.gif "e5f00f4c-cc76-4e8b-9991-b4471f9d4865") ![ポーリングのシナリオ&#40;PollWhileDataFound &#61; &#41; ](../../adapters-and-accelerators/adapter-oracle-ebs/media/ebecf64c-a770-4525-9c75-62fdb71e1fb1.gif "ebecf64c-a770-4525-9c75-62fdb71e1fb1")  

## <a name="differences-between-polling-and-notification"></a>ポーリングと通知の間の相違点  
 ポーリングと通知は、両方の受信操作し、Oracle データベースでデータの変更について、アダプターをクライアントに通知、次の表は、2 つの間のいくつかの違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  


|                                                                                                                                                                                                                                                      ポーリング                                                                                                                                                                                                                                                      |                                                                                                                              Notification                                                                                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                   サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                                                                                                    |                                                                                               通知は、Oracle database バージョン 10.2 以降にのみサポートされます。                                                                                               |
| 一定の間隔でポーリングに使用できるデータを確認するポーリング間隔を構成するかまたは瞬時とタイミング データを使用します。 **ヒント:** ポーリングが継続的に、データの変更が発生したありと設定されるタイミングとしては、各変更の通知しないシナリオでスループットを向上を提供します。 代わりに、その後の前回の変更の通知以降に発生したすべての変更を通知するポーリング間隔を指定します。 |                                                                                                          データの変更通知は瞬時では常にします。                                                                                                          |
|                                                                                                                                         ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングに使用できるとポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。                                                                                                                                         | 通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セット内の変更がある場合は、通知を開始するように指示します。 通知は、Oracle データベースの機能です。 |
|                                                                                                                                                                                                                 ポーリング ステートメントを使用して、読み取りまたは Oracle データベース内のデータを更新することができます。                                                                                                                                                                                                                  |                                                                                             通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。                                                                                             |
|                                                                                                                                                                                                                            ポーリングには、実際のデータが変更されたことについて通知されます。                                                                                                                                                                                                                            |                                                                                   通知が、Insert などのデータの変更の種類にのみ通知は、更新、および削除します。                                                                                    |

 詳細については。  

- ポーリングに関連するバインドのプロパティを参照してください[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

- 使用してポーリング ベースのメッセージを受信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ポーリング Oracle E-business Suite を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)します。  

## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)