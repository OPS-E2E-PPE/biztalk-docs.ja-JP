---
title: "ExportBindings コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6573142e-7ca7-4990-98e3-b7a54840da13
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f12e28b68698aeb42aefa387c94bd76470ecaf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exportbindings-command"></a>ExportBindings コマンド
BizTalk アセンブリ、アプリケーション、またはグループのバインドをエクスポートします。 アセンブリ、アプリケーション、またはグループのバインドと一緒に、グローバル パーティのバインドをエクスポートすることもできます。 (パーティとは、組織のパートナーなど、オーケストレーションと連携するすべてのエンティティを指します。)  
  
## <a name="usage"></a>使用方法  
 **BTSTask ExportBindings/Destination:** *値*[**/grouplevel は**] [**/applicationname は:***値*] [**/AssemblyName:***値*] & #124 です。[**/GlobalParties**] [**/Server:***値*] [**/database:***値*]  
  
## <a name="parameters"></a>パラメーター  
  
|パラメーター|必須|値|  
|---------------|--------------|-----------|  
|**/送信先**(または**/De**、「解説」を参照してください)|はい|作成するバインド ファイルの完全パス (ファイル名を含む)。 同じパスの既存のバインド ファイルは上書きされます。 パスには、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
|**/GroupLevel** (または**/Gr**、「解説」を参照してください)|不可|指定した場合、現在のグループのすべてのバインドがエクスポートされます。 これら 3 つのパラメーターの 1 つだけ指定できます: GroupLevel、ApplicationName、AssemblyName。|  
|**/ApplicationName** (または**/Ap**、「解説」を参照してください)|不可|バインドのエクスポート元のアプリケーション名。 アプリケーションが存在していることが必要です。 名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。 アプリケーション名を確認する際、 **ListApps**コマンドを」の説明に従って[ListApps コマンド](../core/listapps-command.md)です。 このパラメーターを指定しなかった場合、既定の BizTalk アプリケーションが使用されます。 これら 3 つのパラメーターの 1 つだけ指定できます: GroupLevel、ApplicationName、AssemblyName。|  
|**/AssemblyName** (または**/As**、「解説」を参照してください)|不可|バインドのエクスポート元となるアセンブリのローカル一意識別子 (LUID)。 使用してアプリケーションのアイテムの Luid の一覧を表示することができます、 [ListApp コマンド](../core/listapp-command.md)です。 これら 3 つのパラメーターの 1 つだけ指定できます: GroupLevel、ApplicationName、AssemblyName。|  
|**/GlobalParties** (または**/Gl**、「解説」を参照してください)|不可|指定した場合、グループのグローバル パーティ情報がエクスポートされます。|  
|**/サーバー** (または**/S**、「解説」を参照してください)|不可|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
|**/データベース**(または**/Da**、「解説」を参照してください)|不可|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="sample"></a>サンプル  
 **BTSTask ExportBindings/Destination:"C:\Binding Files\MyBindings.xml"GroupLevel/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
## <a name="remarks"></a>解説  
 パラメーターの大文字と小文字は区別されません。 パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。  
  
## <a name="see-also"></a>参照  
 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
 [バインドをエクスポートします。](../core/exporting-bindings6.md)