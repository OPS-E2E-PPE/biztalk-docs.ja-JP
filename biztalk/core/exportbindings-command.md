---
title: ExportBindings コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc0ce7fb54e15028adb76a8edf34d125c064ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345929"
---
# <a name="exportbindings-command"></a>ExportBindings コマンド
BizTalk アセンブリ、アプリケーション、またはグループのバインドをエクスポートします。 グローバル パーティのバインドと共にアセンブリ、アプリケーション、またはグループのバインドをエクスポートすることもできます。 (パーティとは、オーケストレーションと連携する、組織のパートナーなど、すべてのエンティティです)。  
  
## <a name="usage"></a>使用方法  
 **BTSTask ExportBindings/Destination:** *値* **[/grouplevel は]** [ **/applicationname は:** <em>値</em>] [ **/AssemblyName:** <em>値</em>] &#124; **[/GlobalParties]** [ **/Server:** <em>値</em>] [ **/Database:** <em>値</em>]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/変換先**(または **/De**、「解説」を参照してください)|はい|作成するバインド ファイルの完全パス (ファイル名を含む)。 同じパスの既存のバインド ファイルは上書きされます。 パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/GroupLevel** (または **/Gr**、「解説」を参照してください)|いいえ|指定した場合、現在のグループのすべてのバインドがエクスポートされます。 これら 3 つのパラメーターの 1 つだけ指定できます。GroupLevel、ApplicationName、または AssemblyName。|  
|**/ApplicationName** (または **/Ap**、「解説」を参照してください)|いいえ|バインドのエクスポート元のアプリケーション名。 アプリケーションが存在していることが必要です。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名を確認するには、使用することができます、 **ListApps** 」の説明に従って、コマンド[ListApps コマンド](../core/listapps-command.md)します。 このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。 これら 3 つのパラメーターの 1 つだけ指定できます。GroupLevel、ApplicationName、または AssemblyName。|  
|**/AssemblyName** (または **/As**、「解説」を参照してください)|いいえ|バインドのエクスポート元となるアセンブリのローカル一意識別子 (LUID)。 使用して、アプリケーションでアイテムの Luid の一覧を表示することができます、 [ListApp コマンド](../core/listapp-command.md)します。 これら 3 つのパラメーターの 1 つだけ指定できます。GroupLevel、ApplicationName、または AssemblyName。|  
|**/GlobalParties** (または **/Gl**、「解説」を参照してください)|いいえ|指定した場合、グループのグローバル パーティ情報をエクスポートします。|  
|**/サーバー** (または **/S**、「解説」を参照してください)|いいえ|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または **/Da**、「解説」を参照してください)|いいえ|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>コメント  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [バインドのエクスポート](../core/exporting-bindings6.md)