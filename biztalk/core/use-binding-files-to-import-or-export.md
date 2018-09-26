---
title: バインド ファイルを使用して、インポートまたはエクスポートする |Microsoft Docs
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
ms.openlocfilehash: b9ed0f50d6a6d841169b16f3f3ffd485ee345aeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990595"
---
# <a name="use-binding-files-to-import-or-export"></a>バインド ファイルを使用して、インポートまたはエクスポートするには

以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、エクスポートおよびバインド ファイルをインポートすることができます、**パーティ**と**契約**レベル。 以前のバージョンの BizTalk をエクスポートするアプリケーション レベルで説明されています。 

* [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Edi-as2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

このトピックでは、インポートする方法を説明し、パーティ、プロファイル、アグリーメント、フォールバックの設定および詳細を使用してエクスポート[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]と BTSTask します。 

## <a name="overview"></a>概要

インポートおよびエクスポート機能をいくつか挙げます。

* パーティ、ビジネス プロファイル、およびアグリーメントを XML バインド ファイルからインポートします。
* パーティ、ビジネス プロファイル、契約、および EDI フォールバックの設定を XML バインド ファイルにエクスポートします。
* バインド ファイルをインポートするときに、パーティ、またはフォールバックの設定をインポートしない選択したことができます。
* パーティ レベルでインポートすると、関係者と、バインド ファイル内の契約がインポートされます。
* 特定のパーティを同じのバインド ファイルにエクスポートしもこれらのパーティに関連付けられているすべての契約をエクスポートします。
* アプリケーション バインドのインポート ウィザードを使用して、追跡の設定をインポートまたはパーティを削除できます。
* BTSTask が含まれています、`ImportParties`と`ExportParties`コマンド 

## <a name="prerequisites"></a>前提条件

* メンバーであるアカウントでログオンする必要があります、* * BizTalk Server 管理者 * * グループ。 参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  

* 参照を追加する必要があります、 **BizTalk EDI アプリケーション**を BizTalk アプリケーションを EDI アプリケーションとして使用されるからです。 参照してください[構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)します。

## <a name="import-or-export-all-the-trading-partners"></a>インポートまたはエクスポートするすべての取引
1. 開いている**[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、BizTalk グループを展開します。
2. 右クリック**パーティ**、選び**エクスポート**します。 

    エクスポートするとき、**パーティ**-レベル、エクスポートするすべての取引先パートナーです。 ビジネス プロファイル、および XML ファイルに契約を含む取引で使用されるすべてのものもエクスポートされます。 

3. 右クリックして**パーティ**を選択します**インポート**バインディングの XML ファイルを選択します。 

      **を除外するパーティ**、または**EDI フォールバックの設定を除外する**インポートされないようにします。 それ以外の場合、バインド ファイル内のすべてが、インポート、取引先パートナー、ビジネス プロファイル、アグリーメントなど。     

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

参照してください[ImportParties コマンド](../core/importparties-command.md)します。

    
## <a name="export-individual-partners"></a>個々 のパートナーをエクスポートします。
1. **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** **パーティ**です。
2. **パーティとビジネス プロファイル**ウィンドウで、パーティを右クリックし、選択**エクスポート**します。

    特定のパーティをエクスポートするときに、すべてのパーティとパーティで使用されるすべての契約をエクスポートするかの選択肢が提供されます。 オフにすることができます**選択したパーティーと、選択したパーティーのすべての契約をエクスポート**のみを選択するパーティをエクスポートします。

3. **[OK]** を選択します。 

> [!TIP]
> **パーティとビジネス プロファイル**ウィンドウで、使用することも、 **CTRL**と**Shift**キーの一覧で複数のパーティを選択します。 同じバインド ファイルに、選択したパーティのすべてのエクスポートします。

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

参照してください[ExportParties コマンド](../core/exportparties-command.md)します。


## <a name="import-application-binding-file"></a>アプリケーションのバインド ファイルのインポート

アプリケーション レベルでは、EDI および AS2 パーティにバインド ファイルをインポートできます。 

1. **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**、展開**アプリケーション**
2. アプリケーションを右クリックして**インポート**します。
3. **追跡設定をインポート**と**除外パーティ**オプションを使用できます。 これらのオプションを使用して、既存の追跡設定をインポートまたはバインド ファイル内で EDI および AS2 パーティの除外を選択できます。

    | 設定 | 詳細 |
    |---|---|
    |**追跡設定をインポートします。** | メッセージ本文の追跡、およびイベントの追跡など、アプリケーション内でさまざまな成果物に有効になっている追跡設定をインポートします。 <br/><br/>下位互換性を確保するのには、既定で有効にします。 |
    | **パーティーを除外します。**|いないインポートのパーティ、プロファイル、およびアグリーメントは、ファイル内に存在します。 <br/><br/>既定では下位互換性を確保するのには無効です。|

   > [!IMPORTANT]
   > グローバル追跡設定を上書き**追跡設定のインポート**します。 したがって、グローバル追跡を無効にした場合レベル、任意の場合でも、追跡の設定はインポートされません**追跡設定のインポート**がチェックされます。
   > 
   > **BizTalk 設定ダッシュ ボードの [グループ] ページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]について説明します、**追跡設定のインポートを許可する**グローバル設定です。

### <a name="btstask-example"></a>BTSTask の使用例

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

参照してください[ImportBindings コマンド](../core/importbindings-command.md)します。

## <a name="in-this-section"></a>このセクションの内容
インポートまたはエクスポート前のバージョンの BizTalk での EDI および AS2 バインド ファイルを参照してください。 

* [EDI AS2 ソリューションのバインドをエクスポートする方法](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [Edi-as2 ソリューションのバインドをインポートする方法](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
