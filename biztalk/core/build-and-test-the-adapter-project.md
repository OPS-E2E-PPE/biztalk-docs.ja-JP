---
title: ビルドし、アダプター プロジェクトのテスト |Microsoft Docs
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
ms.openlocfilehash: 69f499a3d3dd3bced347525ed91b5a28d2490b59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005811"
---
# <a name="build-and-test-the-adapter-project"></a>アダプター プロジェクトのビルドおよびテスト
AdapterManagement プロジェクトに対して行われたすべての変更をテストするには、プロジェクトをリビルドします。 正常にビルドした後で、アダプター メタデータの追加ウィザードを実行して、内部および外部の XSD ファイルのすべてが AdapterManagement プロジェクトに確実に追加されるようにします。 アダプター メタデータの追加ウィザードの使用方法の詳細については、次を参照してください。[を BizTalk プロジェクトにアダプター メタデータの追加方法](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)します。  

 構成スキーマに対して行われた変更をテストするには、XSD ファイルによって生成された各プロパティ ページを開いて、それらのページが正しいデータを要求し、受け入れるようにします。 これは、送信ポートを構成、受信場所、送信ハンドラー、および受信ハンドラー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール<strong>します。</strong>  

> [!NOTE]
>  アダプターは、構成スキーマのすべてを持っていない可能性があります。 たとえば、メッセージの受信をサポートしていない送信アダプターは、TransmitLocation.xsd および TransmitHandler.xsd スキーマだけを持っている可能性があります。  

### <a name="to-test-the-transmitlocationxsd-file"></a>TransmitLocation.xsd ファイルをテストするには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. 展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**ノード展開**BizTalk グループ**、展開、**送信ポート**に**新規**とクリックして**静的な一方向送信ポート**します。  

3. **送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、送信ポートの名前を入力します。 展開、**トランスポート**ノード、および選択し、**プライマリ**ノード。  

4. 右側のウィンドウでの**トランスポートの種類値**ボックスで、**静的**、順にクリックします**構成**します。 表示された画面には、TransmitLocation.xsd ファイルで指定したフィールドが含まれている必要があります。  

### <a name="to-test-the-receivelocationxsd-file"></a>ReceiveLocation.xsd ファイルをテストするには  

1. 展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**ノード展開**BizTalk グループ**、展開、**受信ポート**コレクション、展開、新しく作成した受信ポート、または受信場所を追加する受信ポートを右クリックし、**受信場所**コレクション、 をポイント**新規**、 をクリックし、**一方向の受信場所**.  

2. **受信ポートの選択** ダイアログ ボックスで、ポートを選択します。  

3. **受信場所のプロパティ**ダイアログ ボックスで、左側のウィンドウで、**全般**ノード。  

4. **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、受信場所の名前を入力します。  

5. **受信場所のプロパティ**ダイアログ ボックスで、右側のウィンドウ、**トランスポートの種類値**ボックスで、**静的**順にクリックします**を構成します。**. 表示された画面には、ReceiveLocation.xsd ファイルで指定したフィールドが含まれている必要があります。  

### <a name="to-test-the-receivehandlerxsd-file"></a>ReceiveHandler.xsd ファイルをテストするには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. 展開、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**ノード展開**BizTalk グループ、** 展開**プラットフォームの設定**、展開**アダプター**、をクリックして**静的**、順にクリックします**BizTalkServerApplication**の方向と**受信**します。  

3. 結果ウィンドウで、受信ハンドラーを右クリックし をクリックし、**プロパティ**します。 **全般**] タブで [**プロパティ**します。 表示された画面には、ReceiveHandler.xsd ファイルで指定したフィールドが含まれている必要があります。  

### <a name="to-test-the-transmithandlerxsd-file"></a>TransmitHandler.xsd ファイルをテストするには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**静的**、順にクリックします**BizTalkServerApplication**の方向と**送信**。  

2. 結果ウィンドウで、受信ハンドラーを右クリックし をクリックし、**プロパティ**します。 **全般**] タブで [**プロパティ**します。 表示された画面には、TransmitHandler.xsd ファイルで指定したフィールドが含まれている必要があります。
