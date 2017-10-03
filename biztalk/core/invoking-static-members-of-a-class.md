---
title: "クラスの静的メンバーを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2128bf6cb71c773cd31be497765e39b0d7815b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoking-static-members-of-a-class"></a>クラスの静的メンバーの呼び出し
既定では、ルール エンジンは、.NET クラスのインスタンスをアサートして、.NET クラスの静的メンバーを呼び出すポリシーを実行するよう要求します。 値を変更することでこの動作を変更することができます、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**次の表に、値のいずれかにします。  
  
|StaticSupport のレジストリ値|ルール エンジンの動作|  
|----------------------------------|--------------------------|  
|0|既定値です。 ルール エンジンは、BizTalk Server 2004 のモデルに従って、.NET クラスのインスタンスがアサートされる場合にのみ、静的メソッドを呼び出します。|  
|1|オブジェクト インスタンスは必須ではありません。 静的メソッドは、ルールが評価または実行されるときに呼び出されます。|  
|2|オブジェクト インスタンスは必須ではありません。 すべてのパラメーターが定数である場合、静的メソッドは、ポリシーの変換時に呼び出されます。 これは最適なパフォーマンスを提供します。なぜなら、条件内の複数のルールで静的メソッドが使用される場合でも、静的メソッドが呼び出されるのは 1 回だけだからです。 アクションとして使用される静的メソッドは変換時に実行されません。代わりに、パラメーターとして使用される静的メソッドが実行される場合があります。|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a>StaticSupport レジストリ キーの追加と変更  
 表示されない場合、 **StaticSupport**下のレジストリ キー **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**、次の手順を実行することによって追加する必要があります。  
  
 **StaticSupport レジストリ キーを追加するには**  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリック**ok**です。  
  
2.  展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**を展開**BusinessRules**、し、 **3.0**です。  
  
3.  右側のペインで右クリックし、**新規**、クリックして**DWORD 値**です。  
  
4.  **名前**、型**StaticSupport**です。  
  
 場合、 **StaticSupport**レジストリ キーが既に存在し、その値を変更するには、次の手順を実行する必要があります。  
  
> [!IMPORTANT]
>  BizTalk が 64 ビット コンピューターにインストールされているかどうかは、追加することができます**StaticSupport**を使用して、次のオプションのいずれかのレジストリ キー。  
>   
>  -   HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 の下を見る必要があります。 このキーが存在するかどうかは、追加することができます**StaticSupport**ここです。  
> -   別のオプションは**StaticSupport**で、 **BTNTsvc [64].exe.config**ファイル、ここで設定がレジストリには何を上書きします。  また、レジストリ設定の変更はオペレーティング システム全体に適用されるのに対し、このオプションでは既定の動作の変更が BizTalk に限定されるので、このオプションの方が好ましいとも考えられます。  
  
 **StaticSupport レジストリ キーの値を変更するには**  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**RegEdit**、順にクリック**ok**です。  
  
2.  展開**HKEY_LOCAL_MACHINE**、展開**ソフトウェア**、展開**Microsoft**、展開**BusinessRules**の順に展開および**3.0**です。  
  
3.  ダブルクリックして、 **StaticSupport**レジストリ キー、または右クリックし、をクリックして**変更**です。