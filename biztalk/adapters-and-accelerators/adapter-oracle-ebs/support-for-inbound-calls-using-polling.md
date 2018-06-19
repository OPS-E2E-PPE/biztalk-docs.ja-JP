---
title: ポーリングを使用して着信サポート |Microsoft ドキュメント
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
ms.openlocfilehash: a8533ce2829fec956819b311fd6b8f99479f40d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217402"
---
# <a name="support-for-inbound-calls-using-polling"></a>ポーリングの受信呼び出しのサポート
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite でのデータへの変更を知らせる Oracle E-business Suite からメッセージを受信するクライアント プログラムを有効にします。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプターが指定された SQL ステートメント、ストアド プロシージャ、関数、または、パッケージ内の手順を実行する、「ポーリング ベース」のメッセージの受信をサポートは、データを取得し、一定の間隔をクライアントに結果を提供時間です。  
  
> [!NOTE]
>  ポーリング操作でのアプリケーション コンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 必須ではインターフェイス テーブルまたはビューのインターフェイスで、操作を実行する場合、アプリケーション、ポーリングの操作のコンテキストを設定します。 アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 使用して一般的なポーリング操作、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次が含まれます。  
  
1.  アダプターのクライアントを指定する必要があります`Polling`で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は**ポーリング**です。  
  
2.  アダプターのクライアントでの SELECT ステートメントを指定する必要があります、 **PolledDataAvailableStatement**ポーリングの使用可能なデータがあるかどうかを判断するプロパティをバインドします。 最初の結果、このステートメントの実行時に返されるセットの最初の行の最初の列に正の整数値が含まれている場合は日付のポーリングに使用できます。  
  
3.  アダプターのクライアントのポーリング間隔を指定する必要があります、 **PollingInterval**間隔を秒単位で指定されたステートメントを定義するプロパティのバインド、 **PolledDataAvailableStatement**プロパティのバインドが実行されます。 ポーリング間隔の最後に、ポーリングされたデータの使用可能なステートメントが実行され、結果セットが返されます。  
  
4.  SELECT ステートメントまたはストアド プロシージャのアダプターのクライアントを指定する必要があります、 **PollingInput**プロパティをバインドします。 テーブルまたはビューをポーリングする場合は、このバインディングのプロパティの SELECT ステートメントを指定する必要があります。 ポーリング ストアド プロシージャを使用する場合は、要求メッセージ全体をこのバインドのプロパティを指定する必要があります。  
  
     内のステートメント、 **PollingInput**によって決定される、ポーリングに使用できるデータが場合にのみ実行プロパティのバインド、 **PolledDataAvailableStatement**手順 2. でプロパティをバインドします。  
  
5.  アダプターのクライアントがポーリング操作に対してアクションを指定する必要があります、 **PollingAction**プロパティをバインドします。 特定の操作のポーリング アクションは、アダプター サービスのアドインを使用して、操作によって生成されるメタデータから判断されます。  
  
6.  アダプターのクライアントが使用できる、 **PollWhileDataFound**ポーリング間隔を無視して継続的に使用可能な場合と、データをポーリングするプロパティをバインドします。  
  
    > [!IMPORTANT]
    >  値を設定した場合、 **PollWhileDataFound**バインド プロパティを True に、アダプターのクライアントを継続的にポーリング プロセスで Oracle からのデータがループ内での Oracle データベースへの接続を開いたり閉じたりします。 ODP.NET によって接続が開かれてレートが閉じられている接続よりも大きいため、しばらく待ってから、接続が使い果たされ、例外がスローされます。 回避策としては、ことを確認の値、 **UseOracleConnectionPool**を True に設定されている適切な値に記載されて、 **IncrPoolSize**接続の数を制御するプロパティのバインドアダプターのクライアントが開けます。  
  
7.  アダプターのクライアントは、用、Oracle PL/SQL ブロック、ポーリング後ステートメントを指定できます、 **PostPollStatement**プロパティをバインドします。 指定されたステートメントの後にこのバインドのプロパティで指定されたステートメントが実行される、 **PollingInput**プロパティのバインドを実行します。  
  
    > [!NOTE]
    >  アダプターで指定されたステートメントの実行、 **PollingInput**と**PostPollStatement**トランザクションのプロパティをバインドします。 内のトランザクションの詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[でアダプターの処理のトランザクションがどのように?](https://msdn.microsoft.com/library/dd788428.aspx)です。  
  
 アダプターは、Oracle E-business Suite から空のポーリング応答を抑制します。  
  
 次の図でポーリング ワークフローに関する情報を提供する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 ポーリング ワークフローの 2 つのシナリオに示します。  
  
1.  ときの値、 **PollWhileDataFound**が"False"(既定の設定) に設定します。  
  
2.  ときの値、 **PollWhileDataFound** "True"に設定されています。  
  
 ![ポーリングのシナリオと #40 です。PollWhileDataFound & #61 です。False &#41;] (../../adapters-and-accelerators/adapter-oracle-ebs/media/e5f00f4c-cc76-4e8b-9991-b4471f9d4865.gif "e5f00f4c-cc76-4e8b-9991-b4471f9d4865") ![ポーリングのシナリオと #40 です。PollWhileDataFound & #61 です。True &#41;] (../../adapters-and-accelerators/adapter-oracle-ebs/media/ebecf64c-a770-4525-9c75-62fdb71e1fb1.gif "ebecf64c-a770-4525-9c75-62fdb71e1fb1")  
  
## <a name="differences-between-polling-and-notification"></a>ポーリングと通知の相違点  
 ポーリング通知、両方の受信操作とは、Oracle データベースでデータの変更について、アダプターをクライアントに通知を次の表には、2 つの間には、いくつか違いが一覧表示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|ポーリング|Notification|  
|-------------|------------------|  
|サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。|通知は、バージョン 10.2 およびそれ以降の Oracle データベースに対してのみサポートされます。|  
|一定の間隔でポーリングの使用可能なデータを確認するポーリング間隔を構成するか、または瞬時に、そのデータが使用可能です。 **ヒント:** ポーリングすれば、スループットを向上させる、データの変更が、継続的に行われていると、発生したタイミングととしてそれぞれの変更の通知を受けるたくないシナリオでします。 代わりに、前回の変更通知以降に行われたすべての変更の通知されるようにすた後ポーリング間隔を指定します。|データの変更通知は瞬時では常にします。|  
|ポーリングは、アダプターによって開始されます。 アダプターでは、データのポーリングを使用し、ポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。|通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セットの変更がある場合に通知を開始するように指示します。 通知は、Oracle データベースの機能です。|  
|ポーリング ステートメントを使用して、読み取るまたは Oracle データベース内のデータを更新することができます。|通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。|  
|ポーリングでは、実際のデータが変更されたことについて通知されます。|Insert などのデータ変更の種類のみ通知を通知は、更新、および削除します。|  
  
 詳細については。  
  
-   ポーリングに関連するバインドのプロパティを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
-   使用してポーリング ベースのメッセージを受信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ポーリング Oracle E-business Suite を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)