---
title: "サービス コンテキスト プロパティの Windows Sharepoint を使用する送信ポートを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- configuring [Windows SharePoint Services adapters], InfoPath forms
- Windows SharePoint Services adapters, Windows SharePoint Services
- InfoPath forms, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], Windows SharePoint Services
- Windows SharePoint Services adapters, send ports
- configuring [Windows SharePoint Services adapters], send ports
- send ports, Windows SharePoint Services adapters
- Windows SharePoint Services, Windows SharePoint Services adapters
ms.assetid: 1ff50fb8-7ba0-47b8-9476-d57413989346
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e766272f33bf23166ba412a76498e4240ab3343b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-send-ports-using-windows-sharepoint-services-context-properties"></a>Windows Sharepoint Services のコンテキスト プロパティを使用して送信ポートを構成する方法
このトピックでは、BizTalk オーケストレーションから Windows Sharepoint Services のコンテキスト プロパティを使用して、実行時に Windows Sharepoint Services 送信ポートを構成する方法について説明します。 同じメカニズムを使用して、Windows SharePoint Services 動的送信ポートと遅延バインディング送信ポートを構成できます。 動的送信ポートの構成プロパティは、実行時にオーケストレーションで設定されます。 アダプターのプロパティで公開されている、 **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスは、動的または遅延バインディング送信ポートにも適用できます。 Windows Sharepoint Services アダプタのコンテキスト プロパティを使用して、動的送信ポートまたは遅延バインディング送信ポートの構成プロパティを設定するには、次の手順を実行します。  
  
### <a name="to-set-configuration-properties-for-a-send-port-using-windows-sharepoint-services-adapter-context-properties"></a>Windows Sharepoint Services アダプタのコンテキスト プロパティを使用して送信ポートの構成プロパティを設定するには  
  
1.  動的送信ポートの動的な一方向送信ポートを作成する手順に従って、トピックの「[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
2.  使用して、**メッセージの割り当て**図形内、**メッセージの構築**送信メッセージの構成プロパティを設定するためのオーケストレーションの図形です。 送信メッセージの構成プロパティを設定する方法の例については、次を参照してください。[チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)です。 **新しいメッセージの構築**このトピックのセクションは、送信メッセージの構成プロパティを設定する方法を示します。 アダプタのコンテキスト プロパティで設定できるプロパティに関連付けられる、 **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスは、次の表に一覧表示されます。  
  
    |トランスポート プロパティ|アダプタのコンテキスト プロパティ|データ型|コメント|  
    |------------------------|------------------------------|---------------|--------------|  
    |アダプター Web サービス ポート|WSS.ConfigAdapterWSPort|int|有効な値は、1 ~ 65535 です。<br /><br /> 既定値は 80|  
    |Timeout|WSS.ConfigTimeout|int|有効値は、1000 ～ 2147483647 です。<br /><br /> 既定値は 100000 です。<br /><br /> 値 0 を指定すると、タイムアウトしないことを表します。|  
    |ターゲット フォルダーの URL|NA|NA|動的ポートは、これは間接的に設定を設定して、 **Microsoft.XLANGs.BaseTypes.Address**オーケストレーションの式図形を使用して動的ポートのプロパティです。 遅延バインディング ポートの場合、このプロパティは常に物理送信ポートの値で上書きされるため、実行時に設定することはできません。|  
    |Filename|WSS.Filename|文字列|以外のトランスポートのプロパティで使用できるすべてのファイル名マクロの使用をサポートしています、 **%filename%**と**%extension%**マクロです。|  
    |名前空間エイリアス|WSS.ConfigNamespaceAliases|文字列|名前空間の別名を正確に実行時に、メッセージの設定には、設定、メッセージがルーティングされる送信ポートの名前空間の別名が一致する場合、名前空間はマージし、およびルーティング エラーが発生します。 この問題を回避するには、指定した名前空間エイリアスが同じにならないようにします。 たとえば、メッセージの名前空間エイリアスを設定するために、オーケストレーションで次の式を使用するとします。<br /><br /> `Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";`<br /><br /> このメッセージは次の値を指定する送信ポートにルーティングされる場合と、 **Namespace エイリアス**プロパティ。<br /><br /> orchns='http://OrderProcess.PurchaseOrder'<br /><br /> この場合、BizTalk Server がメッセージをこの送信ポートにルーティングしようとすると、エラーが発生します。 この問題を解決するのには次の値を指定する可能性があります、 **Namespace エイリアス**送信ポートのプロパティ。<br /><br /> **orchns2**'http://OrderProcess.PurchaseOrder' を =|  
    |Overwrite|WSS.ConfigOverwrite|文字列|有効な値は、<br /><br /> -"yes"<br /><br /> -"no"<br /><br /> "rename"|  
    |SharePoint サイトの URL|WSS.InListUrl|文字列|動的ポートは、これは間接的に設定を設定して、 **Microsoft.XLANGs.BaseTypes.Address**オーケストレーションの式図形を使用して動的ポートのプロパティです。 遅延バインディング ポートの場合、このプロパティは常に物理送信ポートの値で上書きされるため、実行時に設定することはできません。|  
    |Microsoft Office 統合|WSS.ConfigOfficeIntegration|文字列|有効な値は、<br /><br /> -"yes"<br /><br /> -"no"<br /><br /> -"yesformlibrary"<br /><br /> -"optional"|  
    |テンプレート ドキュメント ライブラリ|WSS.ConfigTemplatesDocLib|文字列|なし|  
    |テンプレート フォールバック ドキュメント ライブラリ|WSS.ConfigCustomTemplatesDocLib|文字列|なし|  
    |テンプレート フォールバック名前空間列|WSS.ConfigCustomTemplatesNamespaceCol|文字列|なし|  
    |テンプレート名前空間列|WSS.ConfigTemplatesNamespaceCol|文字列|なし|  
    |[列 `n`]|WSS.ConfigPropertiesXml<br /><br /> 列名設定されて\<PropertyName*x*\>*columnname*\</PropertyName*x* \>フィールドです。|文字列|なし|  
    |[列 `n` の値]|WSS.ConfigPropertiesXml<br /><br /> 列の値が設定されて\<PropertySource*x*\>*columnvalue*\</PropertySource*x* \>フィールドです。|文字列|以外のトランスポートのプロパティで使用できるすべてのファイル名マクロの使用をサポートしています、 **%filename%**と**%extension%**マクロです。|  
  
    > [!NOTE]
    >  コンテキスト プロパティに指定する値は、大文字と小文字が区別されます。 コンテキスト プロパティで動的ポートの構成値を設定するときは、大文字と小文字を正しく使い分けないと、指定した送信ポートにドキュメントがルーティングされるときにエラーが発生します。  
  
3.  オーケストレーションの式図形を使用して設定、 **Microsoft.XLANGs.BaseTypes.Address**プロパティを動的送信ポート。 このプロパティは、動的送信ポートがメッセージをルーティングする URI を指定するために使用されます。 設定する方法の例については、 **Microsoft.XLANGs.BaseTypes.Address**動的送信ポートのプロパティを参照してください、**式を作成**」の「[チュートリアル: モジュール 3 -オーケストレーションから SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)です。 Windows Sharepoint Services アダプタのコンテキスト プロパティの詳細については、次を参照してください。 [Windows SharePoint Services アダプターのプロパティ参照](../core/windows-sharepoint-services-adapter-properties-reference.md)です。  
  
     オーケストレーションで Windows Sharepoint Services 遅延バインディング送信ポートの特定のプロパティを動的に設定することもできます。 その場合、Windows SharePoint Services ポートは 2 回構成されます。1 回は Windows SharePoint Services のコンテキスト プロパティを使用して構成され、もう 1 回は [Windows SharePoint Services トランスポート プロパティ] ダイアログ ボックスを使用して構成されます。 既定では、[Windows SharePoint Services トランスポート プロパティ] ダイアログ ボックスで指定される構成が、コンテキスト プロパティで指定される構成プロパティよりも優先されます。 コンテキスト プロパティで指定される構成を使用するために、次の手順を実行します。  
  
    1.  静的な一方向送信ポートを作成する、トピックの手順に従います[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
    2.  送信ポートのプロパティを設定するときの適切な値を入力して、送信ポートの URI を定義、 **Sharepoint サイト URL**と**送信先フォルダーの URL**プロパティです。  
  
    3.  値を設定、**上書き**プロパティを**オーケストレーション**コンテキスト プロパティによって定義された値を使用するかどうかは**WSS です。ConfigOverwrite**オーケストレーションでします。  
  
    4.  設定、 **Microsoft Office 統合**プロパティを**オーケストレーション**コンテキスト プロパティによって定義された値を使用するかどうかは**WSS です。ConfigOfficeIntegration**オーケストレーションでします。  
  
    5.  値を入力して**-1**のいずれかの送信ポートのプロパティをオーケストレーションのコンテキスト プロパティの値を設定する場合に、整数データ型を使用します。  
  
    6.  オーケストレーションのコンテキスト プロパティを使用して、文字列データ型を使用する送信ポート プロパティの値を設定するには、その送信ポート プロパティを空白のままにします。 これには適用されません、 **Sharepoint サイト URL**と**送信先フォルダーの URL**プロパティです。 これらのプロパティを指定する必要があります、 **Windows Sharepoint Services トランスポート プロパティ** ダイアログ ボックス。  
  
    7.  使用して、**メッセージの割り当て**図形内、**メッセージの構築**送信メッセージの構成プロパティを設定するためのオーケストレーションの図形です。 送信メッセージの構成プロパティを設定する方法の例については、次を参照してください。[チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)です。 **新しいメッセージの構築**このトピックのセクションは、送信メッセージの構成プロパティを設定する方法を示します。  
  
    8.  値 -1 で構成される送信ポート プロパティ (整数データ型を使用するプロパティ)、"オーケストレーション" で構成される送信ポート プロパティ (ドロップダウン列挙プロパティ)、または空白のままの送信ポート プロパティ (文字列データ型を使用するプロパティ) は、オーケストレーションで指定されたコンテキスト プロパティを使用して実行時に設定されます。  
  
 Windows SharePoint Services アダプターを使用して、添付ファイルが埋め込まれた InfoPath フォームを受信した後、SharePoint ドキュメント ライブラリに InfoPath フォームを送信する場合は、次の手順を実行して、フォーム内の InfoPath 処理命令を維持します。  
  
### <a name="to-preserve-infopath-processing-instructions-for-infopath-forms-with-embedded-attachments-processed-by-biztalk-server"></a>BizTalk Server によって処理される添付ファイルが埋め込まれた InfoPath フォームの InfoPath 処理命令を維持するには  
  
1.  を使用する、マップ、オーケストレーション内に 1 つの InfoPath フォームから別の InfoPath フォームにデータをマップする場合は、設定されていることを確認、**処理命令 (Pi) コピー**プロパティへのマップに**はい**です。 このパラメーターが設定されている、**カスタム ヘッダー**のセクションで、**グリッドのプロパティ**マップのページです。  
  
2.  オーケストレーションでマップを使用しない場合は、メッセージの割り当て図形で次の式を使用して出力メッセージを更新します。  
  
    ```  
    NewMessage(XMLNORM.ProcessingInstructionOption) = 1;  
    NewMessage(XMLNORM.ProcessingInstruction) = "<?mso-infoPath-file-attachment-present?>"  
    ```  
  
     上記の式で*新しいメッセージ*処理命令を追加する出力メッセージです。  
  
## <a name="see-also"></a>参照  
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)