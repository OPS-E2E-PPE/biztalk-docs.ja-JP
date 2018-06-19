---
title: インポートまたはエクスポートするバインド ファイルを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22288274"
---
# <a name="use-binding-files-to-import-or-export"></a>バインド ファイルを使用して、インポートまたはエクスポート

以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、エクスポートし、バインド ファイルをインポートすることができます、**パーティ**と**アグリーメント**レベル。 以前のバージョンの BizTalk にエクスポートするアプリケーション レベルで」の説明に従って。 

* [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [EDI AS2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

このトピックの内容をインポートする方法を示し、パーティ、自分のプロファイル、アグリーメント、フォールバックの設定と詳細を使用してエクスポート[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]と BTSTask です。 

## <a name="overview"></a>概要

インポートおよびエクスポート機能があります。

* パーティ、ビジネス プロファイル、およびアグリーメントを XML バインド ファイルからインポートします。
* パーティ、ビジネス プロファイル、アグリーメント、および EDI フォールバックの設定を XML バインド ファイルにエクスポートします。
* バインド ファイルをインポートするときに、パーティまたはフォールバックの設定をインポートしない選択できます。
* インポートする場合はパーティ レベルで、パーティとアグリーメント、バインド ファイル内のみがインポートされます。
* 特定のパーティを同じバインド ファイルにエクスポートし、またそのパーティに関連付けられているすべての契約書をエクスポートします。
* アプリケーションのインポート バインド ウィザードを使用して、追跡設定をインポートするか、パーティを除外するかを選択できます。
* BTSTask を含む、`ImportParties`と`ExportParties`コマンド 

## <a name="prerequisites"></a>前提条件

* メンバーであるアカウントでログオンする必要があります、* * BizTalk Server 管理者 * * グループ。 参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  

* 参照を追加する必要があります、 **BizTalk EDI アプリケーション** EDI アプリケーションとして使用される BizTalk アプリケーションからです。 参照してください[後の構成手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)です。

## <a name="import-or-export-all-the-trading-partners"></a>インポートまたはエクスポートするすべての取引先
1. 開いている**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、BizTalk グループを展開します。
2. 右クリック**パーティ**を選択して**エクスポート**です。 

    エクスポートするとき、**パーティ**-レベル、エクスポートするすべての取引先。 ビジネス プロファイル、および XML ファイルにアグリーメントを含む、取引先で使用されるすべてのものもエクスポートされます。 

3. 右クリックし **パーティ**  **インポート** バインディングの XML ファイルを選択します。 

      選択**除外パーティ**、または**EDI フォールバックの設定を除外する**インポートされないようにします。 それ以外の場合、バインド ファイル内のすべてのインポートされると、取引先、ビジネス プロファイル、およびアグリーメントを含むです。     

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

参照してください[ImportParties コマンド](../core/importparties-command.md)です。

    
## <a name="export-individual-partners"></a>個々 のパートナーをエクスポートします。
1.  **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** **パーティ**です。
2. **パーティとビジネス プロファイル** ウィンドウでは、パーティを右クリックし、選択**エクスポート**です。

    特定のパーティをエクスポートすると、すべてのパーティとそのパーティで使用されるすべての契約書をエクスポートする選択肢が与えられます。 ボックスをオフに**選択した関係者と、選択したパーティ内のすべての契約エクスポート**のみを選択するパーティをエクスポートします。

3. **[OK]** を選択します。 

> [!TIP]
> **パーティとビジネス プロファイル** ウィンドウで、使用することも、 **ctrl キーを押し**と**shift キーを押し**キーを一覧で複数のパーティを選択します。 同じバインド ファイルにエクスポートすべてのパーティを選択します。

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

参照してください[ExportParties コマンド](../core/exportparties-command.md)です。


## <a name="import-application-binding-file"></a>アプリケーションのバインド ファイルのインポート

アプリケーション レベルでは、EDI および AS2 パーティにバインド ファイルをインポートできます。 

1. **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、展開**アプリケーション**
2. アプリケーションを右クリックし **インポート**です。
3. **追跡の設定をインポート**と**除外パーティ**オプションを使用できます。 これらのオプションを使用して、既存の追跡設定をインポートするか、バインド ファイル内の任意の EDI および AS2 パーティの除外を選択できます。

    | 設定 | 詳細 |
    |---|---|
    |**追跡設定をインポートします。** | メッセージ本文の追跡、およびイベントの追跡など、アプリケーション内の各アイテムに有効になっている追跡の設定をインポートします。 <br/><br/>後方互換性を確保するのには、既定で有効にします。 |
    | **パーティを除外します。**|ファイル内で既存いないインポート パーティ、プロファイル、およびアグリーメントでは。 <br/><br/>既定では下位互換性を確保するのには無効です。|

     > [!IMPORTANT] 
     > グローバル追跡の設定をオーバーライド**追跡設定をインポート**です。 したがって、グローバル追跡を無効にした場合レベルに、追跡の設定がインポートされていない場合でも、**追跡設定をインポート**がチェックします。
     > 
     > **BizTalk 設定ダッシュ ボード、グループのページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]について説明します、**追跡設定のインポートを許可する**グローバル設定。

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

参照してください[ImportBindings コマンド](../core/importbindings-command.md)です。

## <a name="in-this-section"></a>このセクションの内容
インポートまたはエクスポートの以前のバージョンの BizTalk の EDI および AS2 バインド ファイルを参照してください。 

* [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [EDI AS2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
