---
title: ビルドし、アダプター プロジェクトのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b5eb486-99ae-4661-b0d0-d2d363d97b73
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dddde1681ab95a4c1fe7b762d7608cac33580411
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233058"
---
# <a name="build-and-test-the-adapter-project"></a>アダプター プロジェクトのビルドおよびテスト
AdapterManagement プロジェクトに対して行われたすべての変更をテストするには、プロジェクトをリビルドします。 正常にビルドした後で、アダプター メタデータの追加ウィザードを実行して、内部および外部の XSD ファイルのすべてが AdapterManagement プロジェクトに確実に追加されるようにします。 アダプター メタデータの追加ウィザードの使用方法の詳細については、次を参照してください。[アダプター メタデータを BizTalk プロジェクトに追加する方法](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)です。  
  
 構成スキーマに対して行われた変更をテストするには、XSD ファイルによって生成された各プロパティ ページを開いて、それらのページが正しいデータを要求し、受け入れるようにします。 これは、構成、送信ポート、受信場所、送信ハンドラー、および受信ハンドラーをする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール**です。**  
  
> [!NOTE]
>  アダプターは、構成スキーマのすべてを持っていない可能性があります。 たとえば、メッセージの受信をサポートしていない送信アダプターは、TransmitLocation.xsd および TransmitHandler.xsd スキーマだけを持っている可能性があります。  
  
### <a name="to-test-the-transmitlocationxsd-file"></a>TransmitLocation.xsd ファイルをテストするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理** ノードを展開**BizTalk グループ**、展開、**送信ポート**に**新規**とをクリックして**静的な一方向送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、送信ポートの名前を入力します。 展開して、**トランスポート**ノードをクリックし、**プライマリ**ノード。  
  
4.  右側のウィンドウでの**トランスポートの種類の値**ボックスで、**静的**、順にクリック**構成**です。 表示された画面には、TransmitLocation.xsd ファイルで指定したフィールドが含まれている必要があります。  
  
### <a name="to-test-the-receivelocationxsd-file"></a>ReceiveLocation.xsd ファイルをテストするには  
  
1.  展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理** ノードを展開**BizTalk グループ**、展開、**受信ポート**コレクション、展開、新しく作成した受信ポートまたは受信場所を追加する受信ポートを右クリックし、**受信場所**コレクション、順にポイント**新規**、クリックして**一方向の受信場所**.  
  
2.  **受信ポートの選択** ダイアログ ボックスで、ポートを選択します。  
  
3.  **受信場所のプロパティ**ダイアログ ボックスで、左ウィンドウで、select、**全般**ノード。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスで、受信場所の名前を入力します。  
  
5.  **受信場所のプロパティ**ダイアログ ボックスで、右側のペイン、**トランスポートの種類値**ボックスで、**静的**順にクリック**構成**. 表示された画面には、ReceiveLocation.xsd ファイルで指定したフィールドが含まれている必要があります。  
  
### <a name="to-test-the-receivehandlerxsd-file"></a>ReceiveHandler.xsd ファイルをテストするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理** ノードを展開**BizTalk グループ、** 展開**プラットフォームの設定**、展開**アダプター**、をクリックして**静的**、順にクリック**BizTalkServerApplication**の方向と**受信**です。  
  
3.  結果ウィンドウで、受信ハンドラーを右クリックし、をクリックして**プロパティ**です。 **全般** タブで、をクリックして**プロパティ**です。 表示された画面には、ReceiveHandler.xsd ファイルで指定したフィールドが含まれている必要があります。  
  
### <a name="to-test-the-transmithandlerxsd-file"></a>TransmitHandler.xsd ファイルをテストするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**静的**、順にクリック**BizTalkServerApplication**の方向と**送信**です。  
  
2.  結果ウィンドウで、受信ハンドラーを右クリックし、をクリックして**プロパティ**です。 **全般** タブで、をクリックして**プロパティ**です。 表示された画面には、TransmitHandler.xsd ファイルで指定したフィールドが含まれている必要があります。