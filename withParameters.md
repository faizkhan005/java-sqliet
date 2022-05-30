                      /**
                       * Get the movies whose actor has apeared more than one time
                       * @param count 
                       */
                      public void getCountGreaterThan(int count){
                                 String sql = "SELECT movie "
                                            + "FROM movies WHERE count(actor) > 1";

                          try (Connection conn = this.connect();
                               PreparedStatement pstmt  = conn.prepareStatement(sql)){

                              // set the value
                              pstmt.setInt(1,count);
                              //
                              ResultSet rs  = pstmt.executeQuery();

                              // loop through the result set
                              while (rs.next()) {
                                  System.out.println(rs.getString("movie"));
                              }
                          } catch (SQLException e) {
                              System.out.println(e.getMessage());
                          }
                      }




![result](https://user-images.githubusercontent.com/67471969/171031847-0f4bf404-d2cb-40c8-ad4b-8913a074feaa.png)
