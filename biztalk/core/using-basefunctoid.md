---
title: BaseFunctoid の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26a54d-20bf-4302-a5cb-b38e4091002b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f56dfac683e9bf10504857bbf705336b9a197c5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993331"
---
# <a name="using-basefunctoid"></a>BaseFunctoid の使用
すべてのカスタム Functoid は、 **BaseFunctoid** クラスから派生する必要があります。 これを行うには、最初にコンストラクターをオーバーライドし、カスタム Functoid に関する情報を BizTalk マッパーに通知する呼び出しのセットを作成します。 次に、Functoid ロジックを記述します。  

## <a name="overriding-the-constructor"></a>コンストラクターのオーバーライド  
 Functoid の特性を設定するには、クラス コンストラクターをオーバーライドするメソッドで、さまざまなタスクを実行する必要があります。 これらのタスクは、ソリューションに必要な Functoid 固有のコードの他に、追加で実行するタスクです。 次の表では、主要なタスクについて説明します。  


|                                                               タスク                                                                |                                        使用するメソッドまたはプロパティ                                        |                                                                                                                                                                                                                                                                                          コメント                                                                                                                                                                                                                                                                                          |
|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                Functoid に一意の ID を割り当てる                                                 |                                                    **ID**                                                     |                                                                                                                                                                                                                                  6000 を超える値のうち、未使用の数値を ID として使用します。 6000 未満の値は、内部 Functoid 用に予約されています。                                                                                                                                                                                                                                   |
|                                          Functoid に副作用があるかどうかを示す                                           |                                              **HasSideEffects**                                               |                                                                                                                                                                                                                                             生成された XSLT コードの最適化のため、マッパーによって使用されます。 このプロパティの既定値は True です。                                                                                                                                                                                                                                              |
|                                                  リソース アセンブリをポイントする                                                   |                                           **SetupResourceAssembly**                                           |                                                                                                                                                                                              プロジェクトと共に、リソース ファイルを含めます。 使用した構築する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、リソース アセンブリである必要があります**ProjectName.ResourceName**します。                                                                                                                                                                                               |
|                                BizTalk マッパーのパレットにカスタム Functoid を表示する                                 |        **SetName**<br /><br /> **SetTooltip**<br /><br /> **SetDescription**<br /><br /> **SetBitmap**        |                                                                                                                                                                                                                                          名前、ツールヒント、および説明用の文字列を表すリソース ID と、16x16 ピクセルのビットマップを使用します。                                                                                                                                                                                                                                           |
|                                           1 つまたは複数のカテゴリに Functoid を割り当てる                                           |                                                 **カテゴリ**                                                  |                                                                                                                                                                                              1 つまたは複数の [Microsoft.BizTalk.BaseFunctoids.FunctoidCategory](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.functoidcategory.aspx) 値を使用して Functoid を分類します。                                                                                                                                                                                              |
|                                             受け取るパラメーターの数を指定する                                             |                **SetMinParams**<br /><br /> **SetMaxParams**<br /><br /> **HasVariableInputs**                | **SetMinParams** メソッドで必要なパラメーターの数を設定し、 **SetMaxParams** メソッドで省略可能なパラメーターの数を設定します。 次のガイドラインに従って値を設定してください。<br /><br /> -省略可能なパラメーター、最小値を設定していない場合は、max を = です。<br />最大数は設定の一部の省略可能なパラメーターがある場合は、(省略可能なパラメーターの最小数のパラメーターの数) を = です。<br />-無制限の省略可能なパラメーターを許可する場合は、最大未設定しないでください。<br />-Min または max、設定されていないと設定は、入力の変数の数がある場合**HasVariableInputs** = `true`します。 |
|                                             Functoid への接続が可能なオブジェクトの種類を宣言する                                             |                                          **AddInputConnectionType**                                           |                                                                                                                                                                                     Functoid がサポートする各 **Microsoft.BizTalk.BaseFunctoids.ConnectionType** に対して、 [AddInputConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) を 1 回ずつ呼び出します。                                                                                                                                                                                      |
|                                             Functoid からの接続が可能なオブジェクトの種類を宣言する                                             |                                           **OutputConnectionType**                                            |                                                                                                                                              [Microsoft.BizTalk.BaseFunctoids.ConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) の値を使用して、Functoid からの出力を受信できるオブジェクトの種類を BizTalk マッパーに通知します。 複数の接続の種類を指定するには **OR** を使用します。                                                                                                                                              |
| Functoid を呼び出すメソッドを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に通知する | **SetExternalFunctionName**<br /><br /> **SetExternalFunctionName2**<br /><br /> **SetExternalFunctionName3** |                                                                                                                     累積 Functoid の場合、 **SetExternalFunctionName** で初期化関数を設定し、 **SetExternalFunctionName2** で累積関数を設定し、 **SetExternalFunctionName3** で累積値を返す関数を指定します。 累積 Functoid 以外の場合、 **SetExternalFunctionName** で Functoid メソッドを設定します。                                                                                                                      |
|  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、インライン コードによって Functoid が呼び出されるようにする  |                                   **AddScriptTypeSupport SetScriptBuffer**                                    |                                                                                                                                             **Microsoft.BizTalk.BaseFunctoids.ScriptType** を指定して [AddScriptTypeSupport](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) を呼び出し、インライン コードを有効にします。 **SetScriptBuffer** を呼び出して、Functoid のコードに渡します。 このコードは、マップにコピーされます。                                                                                                                                              |
|                                          インライン型の Functoid にグローバル変数を宣言する                                          |                                           **SetScriptGlobalBuffer**                                           |                                                                                                                                                                                                                                                     作成した宣言は、マップに含まれるその他のインライン スクリプトで参照可能になります。                                                                                                                                                                                                                                                     |
|                                   インライン型の Functoid に必要なヘルパー関数を示す                                   |                                       **RequiredGlobalHelperFunctions**                                       |                                                                                                                                                                                                              **InlineGlobalHelperFunction** 列挙の値を使用して、必要なヘルパー関数を指定します。 複数のヘルパー関数を指定するには **OR** を使用します。                                                                                                                                                                                                               |
|                                            Functoid に渡されるパラメーターを検証する                                            |                                     **Isdate 関数**<br /><br /> **IsNumeric**                                      |                                                                                                                                                                                                                                                         これらの関数では、例外がスローされることなく、True/False の応答が返されます。                                                                                                                                                                                                                                                         |

## <a name="implementing-functoid-logic"></a>Functoid ロジックの実装  
 Functoid を活用するには、Functoid のカテゴリに応じて 1 つ以上のメソッドを実装する必要があります。 累積 Functoid の場合は、初期化するメソッド、累積するメソッド、および累積値を返すメソッドの 3 つを指定します。 累積 Functoid 以外の場合は、値を返すメソッドを 1 つ指定します。  

 また、Functoid の実装コードをマップにコピーするか、コンパイル済み .NET アセンブリ内にコードを保持して参照によって使用するかを決定する必要があります。  

 次の場合は、インライン型の Functoid の使用を検討してください。  

- ビジネス ロジックが他のユーザーに読み取り可能で、変更される可能性がある場合。  

- Functoid が、マップでサポートされる .NET Framework 名前空間のみに依存する場合。 使用可能な名前空間は、[スクリプトを使用してインライン c#、JScript .NET、および Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)を参照してください。  

- BizTalk ソリューションで別のアセンブリの展開や管理を行わない場合。  

- 変数を共有する一連の Functoid を記述する場合。  

  次の場合は、参照型の Functoid の使用を検討してください。  

- 他のユーザーから参照されたり変更される可能性があるビジネス ロジックを、マップにコピーしない場合。  

- Functoid が、マップでサポートされない .NET Framework クラスに依存する場合。  

- .NET Framework で提供される追加機能を使用するため、BizTalk ソリューションで別のアセンブリを展開したり管理することが妥当な場合。  

## <a name="see-also"></a>参照  
 [参照 Functoid、カスタムの開発](../core/developing-a-custom-referenced-functoid.md)   
 [インラインのカスタム Functoid の開発](../core/developing-a-custom-inline-functoid.md)   
 [カスタムの累積 Functoid の開発](../core/developing-a-custom-cumulative-functoid.md)   
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/Microsoft.BizTalk.BaseFunctoids.BaseFunctoid.aspx)