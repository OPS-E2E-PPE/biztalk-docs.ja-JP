---
title: クラスの静的メンバーの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 419b83518a9a5cbda54326cf757458afbcdd369b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329830"
---
# <a name="invoking-static-members-of-a-class"></a>クラスの静的メンバーの呼び出し
既定では、ルール エンジンは、.NET クラスの静的メンバーを呼び出すポリシーを実行する .NET クラスのインスタンスをアサートすることが必要です。 値を変更することでこの動作を変更することができます、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**次の表の値の 1 つ。  
  
|StaticSupport のレジストリ値|ルール エンジンの動作|  
|----------------------------------|--------------------------|  
|0|既定値です。 ルール エンジンは、.NET クラスのインスタンスがアサートされる場合にのみ、静的メソッドが呼び出された場合、BizTalk Server 2004 のモデルに従います。|  
|1|オブジェクトのインスタンスは必要ありません。 ルールの評価または実行される静的メソッドが呼び出されます。|  
|2|オブジェクトのインスタンスは必要ありません。 すべてのパラメーターは定数である場合、ポリシーの変換時に静的メソッドが呼び出されます。 これは、条件内の複数のルールで使用されている場合でも、静的メソッドを 1 回だけ呼び出しますので、パフォーマンスの最適化です。 変換時に、アクションとして使用される静的メソッドは実行されませんが、パラメーターとして使用される静的メソッドが実行されることに注意してください。|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a>追加と StaticSupport レジストリ キーの変更  
 表示されない場合、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**、次の手順を実行することによって追加する必要があります。  
  
 **StaticSupport レジストリ キーを追加するには**  
  
1. をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリックします**OK**します。  
  
2. 展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**、し、 **3.0**します。  
  
3. 右側のウィンドウで右クリックして**新規**、 をクリックし、 **DWORD 値**します。  
  
4. **名前**、型**StaticSupport**します。  
  
   場合、 **StaticSupport**レジストリ キーが既に存在して、その値を変更するには、次の手順を実行する必要があります。  
  
> [!IMPORTANT]
>  BizTalk が 64 ビット コンピューターにインストールされているかどうかは、追加することができます**StaticSupport**を使用して、次のオプションのいずれかのレジストリ キー。  
> 
> - HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 を確認する必要があります。 このキーが存在するかどうかは、追加することができます**StaticSupport**ここです。  
>   -   配置するもう 1 つの方法が**StaticSupport**で、 **BTNTsvc [64].exe.config**ファイルを設定がレジストリの新機能をオーバーライドします。  さらに、このオプションが優先既定の動作の BizTalk にのみ、分離され、そのためレジストリ設定は、オペレーティング システムのグローバル引数こといずれかのこともできます。  
  
 **StaticSupport レジストリ キーの値を変更するには**  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリックします**OK**します。  
  
2.  展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**を展開し**3.0**します。  
  
3.  ダブルクリックして、 **StaticSupport**レジストリ キー、または右クリックし、をクリックし、**変更**します。