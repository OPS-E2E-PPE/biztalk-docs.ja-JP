---
title: "Windows SharePoint Services 送信ポートを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, send ports
- configuring [Windows SharePoint Services adapters], send ports
- send ports, Windows SharePoint Services adapters
ms.assetid: 7713d3cc-cd8d-43db-8dac-2a7442632b87
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e41aca0c55170de7f8e1514e5a4c77796f48cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-port"></a>Windows SharePoint Services 送信ポートを構成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して Windows SharePoint Services 送信ポートを作成および構成する方法について説明します。  
  
### <a name="to-create-and-configure-a-windows-sharepoint-services-send-port"></a>Windows SharePoint Services 送信ポートを作成および構成するには  
  
1.  BizTalk Server 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**Windows SharePoint Services トランスポート プロパティ**の**型**オプション、**トランスポート**のセクション**一般的な**タブです。  
  
2.  **全般** タブの 、**トランスポート**セクションで、横に**型**、 をクリックして**構成**です。  
  
3.  **Windows SharePoint Services トランスポート プロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |アダプター Web サービス ポート|Windows SharePoint Services アダプタの Web サービスがインストールされる IIS Web サイトの HTTP ポート。 既定では、これは、ポート 80 で構成されている既定の Web サイトです。 他の IIS Web サイトよりも既定の Web サイトに Windows SharePoint Services Web サービスを構成した場合は、この値を更新する必要があります。|  
    |Timeout|Windows SharePoint Services アダプターの Web サービスに対するアダプターのランタイム Web サービス呼び出しに適用されるミリ秒単位のタイムアウト値。 アダプターによって推定される平均値よりもメッセージまたはバッチ サイズが大きい場合、この値を大きくする必要があります。|  
    |ターゲット フォルダーの URL|SharePoint サイトに相対的な Windows SharePoint Services 送信先フォルダの URL。 たとえば、"Share Documents"、"Shared Documents/Purchase Orders/"、"Lists/Tasks" などです。 一覧の URL (Lists/Tasks など) を指定して、メッセージを SharePoint の一覧に送信できます。 送信先に一覧を指定すると、メッセージ本文は一覧のアイテムと共に保存されません。ただし、メッセージから抽出される値は、SharePoint 列に昇格されます。 **注:** SharePoint ドキュメント ライブラリ、リスト、またはフォルダーの URL がその項目の名前と異なる場合があります。 正しい URL を参照するには、Internet Explorer のアドレス バーを確認してください。|  
    |Filename|(省略可能) Windows SharePoint Services ファイル名。 "PurchaseOrder0001.xml" のようなリテラル値または式を入力できます。 式には、リテラル、マクロ、および XPATH クエリを混在させることができます (例 : "PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml")。 ファイル名を指定しない場合、ファイル名は元のファイル名になるか、オーケストレーションによって指定された値が使用されます。ただし、オーケストレーションがファイル名を定義していない場合は、'Msg-%MessageID%.xml' が使用されます。 **注:**一覧へのメッセージを送信、Filename プロパティに指定された値は無視され、SharePoint 列には保存されません。 SharePoint の一覧には、[ファイル名] 列はありません。 代わりに、利用できる 16 列のいずれかを使用して、'Title' 列を更新します。 <br /><br /> 式の詳細については、次を参照してください。 [Windows SharePoint Services アダプター式](../core/windows-sharepoint-services-adapter-expressions.md)です。|  
    |名前空間エイリアス|(省略可能) 名前空間のエイリアスの定義をコンマまたはセミコロンで区切った一覧。 'Filename' や '列の値' のようなフィールドに設定された XPATH クエリで使用される名前空間エイリアスを定義するのにには、このフィールドを使用します。 たとえば、po='http://OrderProcess/POrder', conf='http://OrderProcess/Confirmation' xmlns=""; ipsol='{D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}' です。 **注:**このプロパティは、WSS をオーバーライドしません。ConfigNamespacesAliases メッセージ コンテキスト プロパティが、オーケストレーションによって定義されます。 代わりに、2 つの値が結合されます。|  
    |Overwrite|既存のファイルを上書きするかどうかを設定します。 [はい] を選択すると、既存のファイルを上書きします。 [いいえ] を選択すると、同じ名前のファイルが既に存在する場合にエラーを発生させてメッセージを保留します。 [名前の変更] を選択すると、ファイル名を変更します。 オーケストレーションによって定義される値を使用するには、[オーケストレーション] を選択します。 **注意:** "上書き"プロパティが 'Yes' に設定されているときに、同じ名前を持つメッセージの数が多いでした SharePoint エラーが発生の送信が記録される、イベント ビューアー。 これらのエラーは、アダプタの機能に影響を与えることはありません。 送信できなかったメッセージは再送されます。|  
    |SharePoint サイトの URL|Windows SharePoint Services Web サイトの完全な URL。 たとえば、http://BizTalkServer/sites/TestSite などです。 **注:**の URI を送信ポートまたは受信場所は、256 文字を超えることはできません。|  
    |Microsoft Office 統合|[省略可能] を選択すると、InfoPath などの Office アプリケーションでドキュメントが自動的に開きますが、InfoPath ソリューションが見つからない場合はドキュメントをそのまま保存します。 [はい] を選択すると、InfoPath などの Office アプリケーションでドキュメントが自動的に開きますが、InfoPath ソリューションが見つからない場合はメッセージを保留します。 Windows SharePoint Services InfoPath フォーム ライブラリにメッセージを送信する場合、[はい (InfoPath フォーム ライブラリ)] を選択すると、フォーム ライブラリで検出された InfoPath ソリューションを使用して InfoPath などの Office アプリケーションで自動的にドキュメントが開きます。 ただし、フォーム ライブラリに InfoPath ソリューションが見つからない場合は、メッセージを保留します。 [いいえ] を選択すると、ドキュメントをそのまま保存します。 [オーケストレーション] を選択すると、オーケストレーションによって定義されている値が使用されます。 バイナリ メッセージの場合は いいえ、または省略可能な値を使用する必要があります。 **注:**テンプレート ドキュメント ライブラリのペアを少なくとも 1 つのプロパティと、テンプレート Namespace 列またはテンプレート フォールバック ドキュメント ライブラリとテンプレート フォールバック Namespace 列が必要な Microsoft Office 統合は、[はい] に設定されている場合。|  
    |テンプレート ドキュメント ライブラリ|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を入力します。  たとえば、 `My Solutions`のようにします。 この場所は、一致する InfoPath ソリューションをアダプタが検索する最初の場所です。 ソリューションが見つからない場合、アダプタは、テンプレート フォールバック ドキュメント ライブラリを検索します。 **注:**テンプレート Namespace 列フィールドが空でない場合は、このフィールドは必須です。 **注:**ドキュメント ライブラリの型 '1 行のテキスト '、名前空間が設定されているとこの InfoPath ソリューションで開くことができる XML ドキュメントのルート ノード、または単にルート ノードの少なくとも 1 つの SharePoint 列が必要です。 詳細については、次を参照してください。[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。|  
    |テンプレート フォールバック ドキュメント ライブラリ|InfoPath ソリューションが格納される SharePoint ドキュメント ライブラリの名前を入力します。  たとえば、"Templates" などです。 ソリューションがカスタム テンプレート ドキュメント ライブラリに見つからない場合、アダプタはこのドキュメント ライブラリのみから一致する InfoPath ソリューションを検索します。 [テンプレート フォールバック ドキュメント ライブラリ] フィールドと [テンプレート ドキュメント ライブラリ] フィールドは、2 つのセットの InfoPath ソリューションと組み合わせて使用できます。 すべての一般的な目的に対応する汎用の InfoPath ソリューションと、特定のパートナーで使用する特殊な InfoPath ソリューションがあります。 [テンプレート フォールバック ドキュメント ライブラリ] フィールドでは、汎用のソリューションを指定し、[テンプレート ドキュメント ライブラリ] フィールドでは特定のパートナー向けの特殊な InfoPath ソリューションを指定する必要があります。 **注:**テンプレート フォールバック Namespace 列フィールドが空でない場合は、このフィールドは必須です。 **注:**ドキュメント ライブラリの型 '1 行のテキスト '、名前空間が設定されているとこの InfoPath ソリューションで開くことができる XML ドキュメントのルート ノード、または単にルート ノードの少なくとも 1 つの SharePoint 列が必要です。 詳細については、次を参照してください。[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。|  
    |テンプレート フォールバック名前空間列|InfoPath ソリューションの格納先となるテンプレート フォールバック ドキュメント ライブラリの SharePoint 列の名前。 たとえば、"Namespace" などです。 **注:**テンプレート フォールバック ドキュメント ライブラリ フィールドが空でない場合は、このフィールドは必須です。 **注:**このフィールドは大文字小文字を区別します。|  
    |テンプレート名前空間列|InfoPath ソリューションの格納先となるテンプレート ドキュメント ライブラリの SharePoint 列の名前。 たとえば、"Namespace" などです。 **注:**テンプレート ドキュメント ライブラリ フィールドが空でない場合は、このフィールドは必須です。 **注:**このフィールドは大文字小文字を区別します。|  
    |[列 `n`]|送信先ドキュメント ライブラリに存在する Windows SharePoint Services 列の名前。 この列は、メッセージから抽出される値または "列の値" フィールドで指定される値で更新する必要があります。 **注:** 16 列まで指定できます。 **注:**このフィールドは大文字小文字を区別します。|  
    |[列 `n` の値]|このメッセージに設定する列の値を入力します。 "Purchase Order" のようなリテラル値または式を入力できます。 式には、リテラル値、マクロ、および XPATH クエリを混在させることができます。 たとえば、"%XPATH=//po:POAmount%", "%SendingOrchestrationID%" などです。 **注:**最大 16 個の列値を指定することができます。|  
  
4.  をクリックして**[ok]**と**OK**もう一度設定を保存します。  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services アダプターのプロパティのリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services アダプターの式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [Windows SharePoint Services 列の型のサポート](../core/supported-windows-sharepoint-services-column-types.md)