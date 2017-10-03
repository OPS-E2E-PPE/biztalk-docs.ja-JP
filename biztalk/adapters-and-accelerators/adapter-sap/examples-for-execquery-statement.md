---
title: "EXECQUERY ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft ドキュメント"
description: "EXECQUERY 例と、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するサンプル"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c5d5877ff502b8fdca620d8b92e4427d3b73b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="examples-for-execquery-statement"></a>EXECQUERY ステートメントの例
このトピックでは、EXECQUERY ステートメントの例を示します。  


## <a name="sample-statements"></a>ステートメントの例
-   P1 と P2 の 2 つのパラメーターを受け取るクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   P1 のパラメーターの値の範囲を受け取るクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   特定の範囲外パラメーター P1 の値を取得するクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   パラメーター P1 の 2 つの値のいずれかを実行するクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   パラメーターに特定の値をとることのできないクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     この例では、P1 によって '0000003262' 以外の値をすることができます。 同様に、P2 '0000003263' 以外の値をことができます。  
  
-   SAP システムで定義されているバリアントを持つクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     バリアントは、保存されている SAP クエリの実行中に指定できる選択条件のセットを参照してください。 たとえば、バリアントを使用すると、クエリの既定値を指定します。 すべてのパラメーターの定義のバリアントのクエリでは、コマンド テキストでパラメーターを指定する必要はありません。  
  
-   パラメーターが不要なクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     パラメーターを受け取らないのクエリでは、ダミーの値を持つパラメーターを指定する必要があります。  
  
-   日付の値が必要なパラメーターを含むクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     かかるクエリのパラメーターが日付の値を指定してください、yyyymmdd 形式で指定として日付を指定する必要があります。  
  
-   パラメーターに null 値を指定することによって、クエリを実行するコマンド。  
  
     そのようなクエリとしてクエリを指定することはできません。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     代わりに、値を指定しない場合は、指定しないで P1 にします。  
  
-   値を特定の数より大きい値が必要なパラメーターを含むクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   値が必要なパラメーターを含むクエリを実行するコマンドが特定の数よりも低い。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   値を一定数以上が必要なパラメーターを含むクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   いずれか小さいほうまたは特定の値に等しい値が必要なパラメーターを含むクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   値を特定の数と等しくありませんが必要なパラメーターを含むクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  